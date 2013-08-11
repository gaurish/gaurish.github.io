---
author: gaurish
comments: true
date: 2011-04-17 04:28:49+00:00
layout: post
slug: javascript-bookmarklet-convert-all-text-on-page-into-lower-case
title: '[JavaScript Bookmarklet] Convert All text on page into Lower Case'
wordpress_id: 587
categories:
- Web - JavaScript
tags:
- javascript
---

I was reading a review on amazon and unfortunately the person has posted in all uppercase. I tried to read but all uppercase text is harder to read, not to mention it is considered shouting on the web.In other words, you are reading the text on random site and just want to change it to lowercase. here is how:-

I used clever JavaScript bookmarket to transform all text on the current page into lowercase.


## [Convert text into Lowercase](javascript:(function(){document.body.style.textTransform=%22lowercase%22})();).


Drag the above link to bookmarks bar & click on this whenever you want to convert text into lower caps. quite cool and handy!

the code:
[javascript]document.body.style.textTransform = "lowercase"[/javascript]
