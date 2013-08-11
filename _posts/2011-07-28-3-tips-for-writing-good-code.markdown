---
author: gaurish
comments: true
date: 2011-07-28 13:20:59+00:00
layout: post
slug: 3-tips-for-writing-good-code
title: 3 Tips for writing good Code
wordpress_id: 600
categories:
- Programming
---

Often when I look other people's code, I feel like vomiting. Why? Because most of the time the code is badly written, has bugs & is hard to read. so what is it that makes up "good code". some might say:


> good code = easier to read + lot of comments.


Sure, readability is important but its last thing on my list.

what are the 3 most important things for writing "good code"?



	
  1. **Expect the unexpected**: Sounds oxymoron? But that's what you got to do: Expect all cases. Practically what this means is you have to do error handling & validation at every step of program. Example, Don't just assume connection to database works now, so it will work forever. if you are passing a type array to a class method, don't assume in that method will receive that argument of array type,. things can go wrong anytime. Always be prepared to _Expect Everything! Check Everything_

	
  2. **Exploit your own code**: As programmers our mind always focuses on how to make things work which is fine but this leads so to locked mindset; trained to think in just one way. This is specially bad from security standpoint. An Excellent example is bug in opensource [blowfish C Libary](http://www.schneier.com/blowfish-bug.txt). This bug existed from 1998, nearly 13years in which hundreds of highly talented developers must have looked at the code & yet not noticed the bug. Wonder Why? Because when reading the code, we are reading the programmers indent instead of actually seeing what the code is doing. What we should be doing is trying to break our own code: think of all possible way you can bypass & do something dangerous. essentially think like a cracker/hacker. If you can't develop that mindset -- make sure atleast one person from your team can

	
  3. **Never Trust the Client: **_never ever trust the client!_ By client I mean web browser etc. This means any data retuned from functions you have written in javascript have to  validated again server side. Don't trust any data that is sent by client & always sanitize your inputs. Because people can modify headers, edit form values, change javascript logic completely. so its very important that you always double-check everything on server & make sure its what you expect.developers should treat web browsers as hostile environment over which they have partial non-exclusive control.




So these were my 3 tips for writing _good code_. The others can be Better Docs,making code readable, performance but the Above 3 according to me are most important.  What you think? Let your thought in comments below
