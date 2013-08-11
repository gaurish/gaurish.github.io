---
author: gaurish
comments: true
date: 2010-12-28 23:25:16+00:00
layout: post
slug: javascript-5-things-love-hate
title: 'JavaScript: I hate you but I Love you, too'
wordpress_id: 516
categories:
- Programming
- Web - JavaScript
---

##  

[caption id="attachment_520" align="aligncenter" width="300" caption="5 things I love & Hate about JavaScript"]![JavaScript: 10 things I love & Hate](http://www.gaurishsharma.com/wp-content/uploads/2010/12/lovehate-300x211.jpg)[/caption]

Introduction






[JavaScript ](http://en.wikipedia.org/wiki/JavaScript) was developed by Netscape for their Netscape browser way back in 1995(which is like century in web development ). As we all know [Netscape browser is dead](http://blog.netscape.com/2007/12/28/end-of-support-for-netscape-web-browsers/) but language has managed to live and has propagated into all major browsers.  JavaScript which was a Toy Language until recently, but now it been getting its much deserved attention.  It would be save to say, that if there is anything exciting happening in web development  arena- its JavaScript. JavaScript is Hot! this is the reason, I am been reading on JavaScript a lot these days. this post will summarize - 10 things I love and hate about JavaScript.


## This is what I HATE:-





	
  1. **Missing Class Concept**: About the language syntax, JavaScript is different than classical programming languages like C/C++,Java,Python that we have grown up with. It takes different design approach. coders coming from popular Object-Oriented background will find it odd that that there is no concept of <!-- more -->class in JavaScript. Functions are first-class citizens. while this works well for small projects. But when managing and deploying large javascript apps it becomes an issue.as you will miss goodies like auto-loading classes and might have resort to coding a server side construct just for loading correct JS files.

	
  2. **It can be Disabled**: As you all know,at flick of a button; user candisable JavaScript. this is single biggest annoyance  I have with JavaScript. while developing any Javascript, web devs have to work around this hard fact and often do same thing twice i.e once client side & once on server-side which takes lot more effort.

	
  3. **Global Namespace: **JavaScript has the concept of implied global variables. What it means is if you don't declare a variable with _var <variable name>_, it would automatically assume that its a global variable. Further everything has Global Scope. every script we load ends up  polluting Global namespace and might lead to Cross-site scripting attacks(XSS) and other bad things can happen.

	
  4. **Stupid Name: **Javascript is the worst possible name for a programming language for browser. Why, because going by name it sounds that Javascript is a subset of Java or atleast is related to Java.And it ends up confusing lot of people. The fact is Javascript is standalone programming language which has no relation to Java.

	
  5. **Bad Implementations:** It deeply annoys me that same  JavaScript code works differently across all browsers. may be because different browser have different js engines.But the fact is this just makes programming in plain JavaScript hard. But thanks to some angels who rescued us by creating really awesome JavaScript libraries like jQuery,YUI,Prototype,Mootools etc. These frameworks hide all the platform and browser specific ugliness and restore some sanity back into programmers mind. its due to these libraries that people don't treat JavaScript as a "Toy" language. And also due to the fact that Javascript support across all browsers has improved dramatically.




## This is what I LOVE:-





	
  1. **Makes Web interactive**: JavaScript is not just any other programming language out there, its a special language. it gives browser  some interactivity. JavaScript is like a wheel, on which ajax driven sites like Gmail,Google Maps are able to run so interactively that it makes them viable alternative to Desktop Applications. JavaScript plays a big role in making web what is is today.

	
  2. **Functions are first class citizens: **Function in JavaScript are considered objects like any other onbject which are part of language, which include _Numbers,Strings_ etc. the advantage of this is a Javascript _Function _can be Assigned to Variables, as property of another object, as parameter, returned as function result. they can even be created using literals. the fact that javascript functions can interact directly with other object gives you immense flexibility & power.

	
  3. **Objects as name/value pairs: **In JavaScript, Objects can be seen Hash table which contain name/value pairs. At first this may sound boring but I think a mash-up of has tables and objects is a great idea. Because an Object can also be a container for other objects and you can keep nesting other objects to make a logical structure. to declare a new empty object the syntax  as under [javascript]var objectName = new Object();[/javascript]

this is a an empty object, to fill this up you will have simple assignment using equals sign

[javascript]objectName.property1 = 'String value';
objectName.property2 = 1989;
objectName.property3 = new Date(2010,12,12);
[/javascript]

	
  4. **Callbacks**: Javascript has this concept of callbacks, in other languages that I have known the concept is not used much. Javascript uses callbacks everywhere. callbacks are pretty handy if you are doing asynchronous programing(Hint: browser always behaves  asynchronously after page is loaded). here is an example of callback [javascript]setTimeout(function() { alert('Callback fired');},3000);[/javascript]

. In this example, what essentially we are doing is called _setTimeOut_ with timeout value of 3second and passing no name function as parameter for callback. What this does is, after 3seconds it will callback to function and show an javascript alert box. pretty simple yet very useful

	
  5. **Loose typing,Closures & prototypical inheritance: **I know I cheated,this isn't just one feature but these 3 separate things I like about javascript.

	
    * **Loose Typing: **loose typing simply means can that you can declare variables without declaring its type. And that variable will have the type defined on basis on the value it holds, so if variable holds string value. its a string. now, I am not saying Loose typing is the best thing because all C/C++ & java programmers will kill me but I think loose typing makes coding bit easier and that's why I prefer it over strong typing

	
    * **Closures**: simply put, closure is a Function instance coupled with the local variables from its environment that are necessary for its execution. I know this is an new concept for from most people trying to learn javascript, but  its one of the most powerful features of javascript.

	
    * **Prototypical inheritance: **Even without any concept of classes, JavaScript does have inheritance where instead of  subclassing, objects inherit directly from other objects without using any classes.Infact, Javascript is the only mainstream language that uses prototypical inheritance





So these are 5 things that I liked and hate about JavaScript. do let me know yours
