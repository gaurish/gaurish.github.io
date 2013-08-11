---
author: gaurish
comments: true
date: 2012-04-22 19:48:23+00:00
layout: post
slug: new-ruby-1-9-hash-syntax
title: New Ruby 1.9 hash syntax
wordpress_id: 678
categories:
- Programming
- Ruby
---

Ruby 1.9 has a cool hash syntax which is quite similar to javascript, so the following hash

[ruby]
hash = {:symbol => "value"}
[/ruby]

can be written as

[ruby]hash = {symbol: "value"}[/ruby]

now, what if both key & values are symbols, in ruby 1.8 & before you would write

[ruby]
:pick => :any
[/ruby]

but now, this could be written in short form as

[ruby]
pick: :any
[/ruby]

And this both new & old syntax for hash are supported in ruby 1.9, you can use whatever syntax you are comfortable the most but it helps to know both forms of syntax specially when reading the code that other might have written. personally, I like the new one -- fewer characters to type :P



PS: this new has syntax is applicable only if the_ key is a :symbol. _In case when key is not a symbol. you have to still stick with old array syntax(_=>)_
