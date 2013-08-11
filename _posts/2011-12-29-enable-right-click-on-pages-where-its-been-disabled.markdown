---
author: gaurish
comments: true
date: 2011-12-29 10:46:03+00:00
layout: post
slug: enable-right-click-on-pages-where-its-been-disabled
title: Enable right-click on pages where its been disabled
wordpress_id: 637
categories:
- Web - JavaScript
---

My bank has a stupidly disabled right-click on its website which I don't like.

[caption id="attachment_638" align="aligncenter" width="150" caption="No Right-Click Allowed"][![No Right-Click Allowed](http://www.gaurishsharma.com/wp-content/uploads/2011/12/Capture-150x150.png)](http://www.gaurishsharma.com/wp-content/uploads/2011/12/Capture.png)[/caption]

So I created clever JavaScript bookmarket to disable this restriction


## [Remove disable right-click restriction](javascript:void(document.oncontextmenu=null))


Drag the above link to bookmarks bar & click on this when you want to enable right-click on pages where its been disabled!

here is the code:

[javascript]
javascript:void(document.oncontextmenu=null)
[/javascript]
