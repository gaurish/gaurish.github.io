---
author: gaurish
comments: true
date: 2011-10-01 16:48:36+00:00
layout: post
slug: php-calculate-age-in-days
title: '[php] Calculate Age in Days'
wordpress_id: 622
categories:
- PHP
- Programming
---

Just today while driving back home, a random question came across my mind,


## What is my age in number days?


Now, I am not good at maths to figure it out manually but since I am decent php programmer, I wrote this small code snippet which helps calculate my age counting in terms days. And its just one line!

[php]
$birthday = '1989-03-06';
$now = date("Y-m-d");
echo 'You are '. date_diff(date_create($birthday), date_create($now))->format('%a days old');
[/php]

So according to this,
**Today is the 8,244th day of my life**. Cheers! :D
