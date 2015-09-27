---
layout: post
title: "Guide for Using ARel in Rails Where ActiveRecord Doesn't Cut It"
description: "A Guide for using ARel"
---

ARel is a database agnostic library that ActiveRecord record uses under the covers. It can be used to generate advanced SQL queries.

## ActiveRecord Public API
ActiveRecord handles majority of the use-cases pretty well. for example, you want to use ActiveRecord for:


### Searching for equality

```ruby
> Post.where title: 'hello'
# SELECT "posts".* FROM "posts"  WHERE "posts"."title" = 'hello'
```

### Searching for NULLs

```ruby
> Post.where title: nil
# SELECT "posts".* FROM "posts"  WHERE "posts"."title" IS NULL
```

### Searching for either of given values
suppose I want to search where title is 'hello' OR 'hi' OR 'howdy'. pass all options as an array works

```ruby
> Post.where title: ['hello', 'hi', 'howdy']
# SELECT "posts".* FROM "posts"  WHERE "posts"."title" IN ('hello', 'hi', 'howdy')
```

#### Searching for either given values or NULLs

```ruby
Post.where title: ['hello', 'hi', 'howdy', nil]
# SELECT "posts".* FROM "posts"  WHERE (("posts"."title" IN ('hello', 'hi', 'howdy') OR "posts"."title" IS NULL))
```

### Searching for Range, where values are BETWEEN given starting & end values
suppose I want to search all posts published in last 2months


```ruby
> Post.where publishing_date: 2.months.ago..Date.today
# SELECT "posts".* FROM "posts"  WHERE ("posts"."publishing_date" BETWEEN '2014-04-09 04:25:23.704466' AND '2014-06-09')
```

### Searching for NOT
Starting Rails 4, ActiveRecord has [`not`](http://api.rubyonrails.org/classes/ActiveRecord/QueryMethods/WhereChain.html#method-i-not) which will negate the query, so all of the above queries when appended with `not`, will work like this:

```ruby
> Post.where.not(title: 'hello')
# SELECT "posts".* FROM "posts"  WHERE ("posts"."title" != 'hello')

> Post.where.not(title: nil)
# SELECT "posts".* FROM "posts"  WHERE ("posts"."title" IS NOT NULL)

> Post.where.not title: ['hello', 'hi', 'howdy']
# SELECT "posts".* FROM "posts"  WHERE ("posts"."title" NOT IN ('hello', 'hi', 'howdy'))

> Post.where.not title: ['hello', 'hi', 'howdy', nil]
# SELECT "posts".* FROM "posts"  WHERE (NOT (("posts"."title" IN ('hello', 'hi', 'howdy') OR "posts"."title" IS NULL)))

> Post.where.not publishing_date: 2.months.ago..Date.today
# SELECT "posts".* FROM "posts"  WHERE (NOT ("posts"."publishing_date" BETWEEN '2014-04-09 04:58:40.232850' AND '2014-06-09'))
```

What about queries with that require `LIKE`, `<`(less than), `>`(greator than), `<=`(less than equal to), `>=`(greator than equal to) operators?

As you might have guessed ActiveRecord doesn't support generating queries with above operators, so what you do?




### More operators that you might need:
While working with SQL databases, you might feel the need to use the following operators.

 1. **LIKE**:  used when to search a specific pattern
 2. **`<`(less than)**: Less than
 3. **`>`(greator than)**: Greater than
 4. **`<=`(less than equal to)**: Less than or equal
 5. **`>=`(greator than equal to)`**: Greater than or equal

But ActiveRecord doesn't support them. you could use "strings". But what if your queries need certain amount of conditional in ruby? Enter ARel - ActiverRecord's private API

### Arel methods/predicates that are available for above 5operators
1. **Like**: `matches`
2. **Less than**: `lt`
3. **Greater than**: `gt`
4. **Less than or equal**: `lteq`
5. **Greater than or equal**: `gteq`

To be correct, [there are more](https://github.com/rails/arel/blob/master/lib/arel/predications.rb) but they are rarely used.

Before we see each of the methods in details, lets first look on how to install/use ARel gem.

### How do I install ARel?
if you are using Rails/ActiveRecord, its already installed & configured! Every ActiveRecord model is backed by an Arel Table. try calling `arel_table` method on any ActiveRecord model. Object retuned will be instance of `Arel::Table` as shown in the example below.

```ruby
> arel = Post.arel_table
 => #<Arel::Table:0x00000101740160 @name="posts", @engine=Post(id: integer, title: string, body: text, publishing_date: date, published: boolean, created_at: datetime, updated_at: datetime), @columns=nil, @aliases=[], @table_alias=nil, @primary_key=nil>

```

## Examples

#### Match/Like operator
Use this when you want to match a part of the string, so instead of this:

```ruby
Post.where('title like ?', '%welcome%')
# SELECT "posts".* FROM "posts"  WHERE (title like '%welcome%')
```

you can do this

```ruby
Post.where arel[:title].matches('%welcome%') #arel = Post.arel_table
```

Will skip string examples for brevity's sake
#### Less Than Operator - `lt`

```ruby
Post.where(arel[:created_].lt 1.day.ago).to_sql
"SELECT `posts`.* FROM `posts`  WHERE (`posts`.`created_at` < '2015-09-26 16:19:31')"
```

#### Greater Than Operator - `gt`

```ruby
Post.where(arel[:created_].gt 1.day.ago).to_sql
"SELECT `posts`.* FROM `posts`  WHERE (`posts`.`created_at` > '2015-09-26 16:19:31')"
```

#### Less than or equal Operator - `lteq`

```ruby
Post.where(arel[:created_].lteq 1.day.ago).to_sql
"SELECT `posts`.* FROM `posts`  WHERE (`posts`.`created_at` <= '2015-09-26 16:19:31')"
```

#### Greater than or equal Operator - `gteq`

```ruby
Post.where(arel[:created_].gteq 1.day.ago).to_sql
"SELECT `posts`.* FROM `posts`  WHERE (`posts`.`created_at` >= '2015-09-26 16:19:31')"
```

## Real world Use-Case
Consider the following AR scope

**String version**

```ruby
  scope : find_valid_phones_to_whom_we_can_text, -> { where(duplicate: false)
    .where("notification_type = 'mobile' OR notification_type = 'phone' OR notification_type = 'office_phone'")} do
    def whitelisted
      # fetches only those records whose contact number is valid
      # contact number should not start from 800, (800)
      # contact number should not be more than 10 characters
      # contact number should not contain extension number like (1-2 x 2345)
      query = []
      # an array of numbers where we don't want to send sms
      BLACKLISTED_NUMBER_PREFIXES.each do |prefix|
        if query.empty?
          query << "(contact NOT LIKE '#{prefix}%' AND contact NOT LIKE '(#{prefix})%')"
        else
          query << "(contact NOT LIKE '#{prefix}%' AND contact NOT LIKE '(#{prefix})%')"
        end
      end
      query << "NOT length(contact) > 10"

      where(query.join(" AND "))
    end
  end
```

**Arel Version**

```ruby
  scope : find_valid_phones_to_whom_we_can_text, -> { where(duplicate: false)
    .where(notification_type: ['mobile', 'phone', 'office_phone']) } do
    # fetches only those records whose contact number is valid
    def whitelisted
      contact = Notification.arel_table[:contact]
      # contact number should not be more than 10 characters
      has_valid_length = Arel::Nodes::NamedFunction.new('length', [contact]).lteq(10)
      # contact number should not start from 800, 888 etc
      where( contact.does_not_match_any(BLACKLISTED_NUMBER_PREFIXES)
        .and( has_valid_length ))
    end
  end
```

As you can see above, Arel version reads better.


## Wrapping Up
Arel full fledged query generator which generate any SQL query. Should you use? Like all things in computer science. the answer is _it depends_ on the use-case.

1. SQL that ActiveRecord can generate: Use ActiveRecord.
2. SQL that ActiveRecord can't generate but doesn't have dynamic conditional logic. Use Strings.
3. SQL that ActiveRecord can't generate & also have dynamic conditional logic based on paremeters: Use AREL as shown in the above real-world example

To conclude, I would say Arel is tool that every rails developer should have in their toolbox.

Lastly,
This is a blog post written after an year's gap. so any feedback/comments/questions are welcome by tweeting to me at [@gaurish](https://twitter.com/gaurish)

