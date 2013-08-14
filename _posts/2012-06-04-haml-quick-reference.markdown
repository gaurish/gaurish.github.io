---
author: gaurish
comments: true
date: 2012-06-04 14:05:58+00:00
layout: post
slug: haml-quick-reference
title: HAML Quick reference
wordpress_id: 699
categories:
- Programming
- Ruby
tags:
- HTML
---

## This would serve as a quick reference for HAML.



HAML is a markup language that gets transformed into HTML. you may ask, why not write write my code in HTML, What's wrong with HTML? And how does HAML solve does the problem?![HAML_logo](http://upload.wikimedia.org/wikipedia/commons/3/3b/Haml_1-5_logo.png)


### Problem with HTML


HTML is verbose & becomes hard to maintain specially, if you have a large site. To see why HTML's verbosity is issue, consider this example:

**HTML**

{% highlight html %}
<div id="profile">
<div class="left column">
<div id="date"><strong>4th June 2012</strong></div>
<div id="address"><em>Jaipur, India</em></div>
</div>
<div class="right column">
<div id="email"><a href="www.example.com">example.com </a></div>
<div id="bio">Rails Developer</div>
</div>
</div>
{% endhighlight %}

As you may notice, there are couple of issues with html:


	
  1. Every starting tag has to have a ending tag
  2. The number of words & lines are more
  3. plain HTML is pain to write & read






Now, compare this to HAML which basically does the same thing but in lot more human readable form

{% highlight haml %}
#profile
.left.column
#date
       %strong 4th June 2012
#address
       %em Jaipur, India
.right.column
#email
       %a{:href="www.example.com"}
            example.com
#bio   Rails Developer
{% endhighlight %}

So in short,







#### Syntax     -  Description
 - `%tag_name` - produces opening & closing tags
 - `%tag_name.class_name` - add a class attribute to given tag
 - `%tag_name#id_name` - adds a id attribute to given tag
 - `-`    - runs the native code(ruby etc) but doesn't not display result
 - `=`   - runs the native code(ruby etc) and display output

Example:

`#body` - Produces div tag with id="body" as div tag is default

For more, kindly refer to [HAML official site](http://haml.info/)
