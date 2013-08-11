---
author: gaurish
comments: true
date: 2013-04-09 12:10:25+00:00
layout: post
slug: understanding-differences-between-symbols-strings-in-ruby
title: Understanding Differences Between Symbols & Strings in Ruby
wordpress_id: 794
categories:
- Guides and Howtos
- Programming
- Ruby
---

The Ruby Programming language has two different ways by which you can represent strings in your programs:



	
  1. String

	
  2. Symbol




IMO, This stuff is the most confusing to people who are new to ruby & a friend of mine recently asked me to explain it(hence this blog post). so I am this post we will talk about the following:








	
  1. what is a symbol?

	
  2. The main differences between symbol & string?

	
  3. When to use symbol instead of string?










so, without wasting further time, here is the brain-dump of my explanation on symbols vs strings in ruby




### What is a symbol?


A symbol is a string which is prefixed colon at starting. In other words, if you take ruby string such as "gaurish", 'gaurish sharma' or "gaurish-sharma" & prefix a colon(':') at te start, you get a symbol.  here is can example.


### Two ways to do the essentially the same thing. Why?


Yes, you guessed it right. Strings & Symbols are essentially the thing. so why have two diffident "types" to represent string? The reason is how strings are implemented in ruby.


> In Ruby, Everything is a Object including Strings


Due to SmallTalk influence, Ruby is fully object oriented language & there are no primitive types. Everything is implemented as Objects. so, when ever you try to assigned a string value to an variable like this `x = "foo"`, you are creating a new object in memory. Here is an small program which allocates same string to a variable 1,000 times & prints `object_id` of each string

{% gist 5344872 strings.rb %}
{% gist 5344872 term_output.rb %}

As you may notice from terminal output of this program/script that each string has different object_id. ruby does creates a new object in memory every single time even thought the string is the same.



#### Wonder, if there is a another way?



How can I have strings which create object in memory once & all later operations refer to that previously created object with same object_id?

Glad: you asked. Enter Symbols! here is the same program with symbols.
{% gist 5345032 symbol.rb %}
{% gist 5345032 term_output.rb %}

In contrast with string, Notice how object_id is same for symbols which means its the same symbol.


### What are the differences between Symbols & Strings?





	
  1. Symbols are immutable: Their value remains constant.

	
  2. Multiple uses of the same symbol have the same object ID and are the same object compared to string which will be a different object with unique object ID, everytime.

	
  3. You can't call any of the String methods like `#upcase`, `#split` on Symbols.




### When to use symbol instead of string?


Symbols generally have performance benefits. so will see their usage almost everywhere including getters & setters in classes, hash keys etc. here is few examples

{% highlight ruby %}
#you will NEVER see this
class Foo
  attr_reader "name"
end
{% endhighlight %}

{% highlight ruby %}
# Instead, you will ALWAYS see a symbol
class Foo
  attr_reader :name
end
#same thing but symbols are faster than strings
{% endhighlight %}


#### to use strings when:





	
  1. you want to use any of string methods like #upcase, #split, #downcase etc.

	
  2. you want to change/mutate the string




#### to use Symbols when:	
1. symbols can't be changed at runtime. If you need something that absolutely, positively must remain constant
	
2. Places where same string is going to be repeatably used, example hash keys are pretty good candidate for symbols. so instead of string keys,`hash["key"] = value`. you should  use symbols like this  `hash[:key] = value`





To conclude, strings & symbols in ruby are similar but differences given above. But the main difference is that symbols are immutable &   slightly more performant than strings so you should you them place where you know same string is likely to be repeated again & again. 
