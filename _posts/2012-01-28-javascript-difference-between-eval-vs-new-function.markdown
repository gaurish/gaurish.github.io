---
author: gaurish
comments: true
date: 2012-01-28 07:04:20+00:00
layout: post
slug: javascript-difference-between-eval-vs-new-function
title: '[JavaScript] Difference between eval() vs new Function()'
wordpress_id: 654
categories:
- Web - JavaScript
---

Many JavaScript programmers treat eval & new Function construct as the same. But new Function & eval are NOT the same. the important difference is:-



	
  * **eval()** works within the current execution scope and can affect local variables.

	
  * **new Function() **cannot affect local variables because the code runs in a separate scope


So both are evil & should only be used when there is no other way but as you may notice new Function is slightly less evil
