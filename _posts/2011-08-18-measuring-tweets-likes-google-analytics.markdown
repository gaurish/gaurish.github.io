---
author: gaurish
comments: true
date: 2011-08-18 10:47:10+00:00
layout: post
slug: measuring-tweets-likes-google-analytics
title: '[How To] Track Tweets & Likes through Google Analytics '
wordpress_id: 610
categories:
- Web - JavaScript
---

**Google Analytics (GA)** is a free service offered by [Google](http://en.wikipedia.org/wiki/Google) that generates detailed [statistics](http://en.wikipedia.org/wiki/Statistics) about the visitors to a [website](http://en.wikipedia.org/wiki/Website). Its hugely popular tool which is used 57% of the 10,000 most popular websites on the currently, the list includes Twitter,myspace etc. GA tracks visitors & provides you useful information such as



	
  * **Traffic source**: If it was direct traffic, Purchased traffic via Ads or some other source

	
  * **Information about Visitor**: Their IP Address, country, Browser,time spend on site & lots of other information that could help you understand your visitors

	
  * And lots of other such useful bits of information.




What GA could not track until recently was social engagement, if someone click Like button,tweets or shared your site on social network. How do you track it? by default that social media traffic would be shown as DIRECT traffic which is not what you want.  But good news is Google analytics now support this and they are calling this __trackSocial_ method






the syntax is as follows:<!-- more -->



_trackSocial(network, socialAction, opt_target, opt_pagePath)

Where:



	
      1. **Network**: Name of the social network ( facebook, twitter, etc)

	
      2. **SocialAction**: Type of action (like, tweet, send,)

	
      3. **opt_target**: Subject of the action being taken. Optional, defaults to the URL being shared (document.location.href). Can be manually set to anything: a different URL (if they’re sharing content that “points” to another URL), an entity (e.g, product name, article name), or content ID

	
      4. **opt_pagePath**: The page on which the action occurred. Optional, defaults to the URI where the sharing took place (document.location.pathname). Can be manually set (like a virtual pagename).









I was tasked to implement this feature on a client website, so they can see social interactions in Google Analytics. here is how I did it:




## Basics


Facebook & twitter does not want to share their data with Google but it seems google has figured out a way.  basically,  __trackSocial_ i sJavaScript based integration & Its not that complex. what we gotta do is to bind callback functions to javascript events. these events could facebook like/unlike, facebook send & twitter tweet. These callback function would be then invoked whenever user generated an social media related event. using this function callback GA script knows that action of tweeting,liking has taken place & GA sent sents the tracking beacon.


## What you need





	
  * Google Chrome Browser

	
  * [Google Analytics Debug Extension](https://chrome.google.com/webstore/detail/jnkmfdileelhofjcijamephohjechhna)

	
  * Basic JavaScript knowledge




### The Process:


Read the [Google supplied guide](http://code.google.com/apis/analytics/docs/tracking/gaTrackingSocial.html) which describes how to use Google Analytics to get interaction metrics on non-Google networks such as Facebook and Twitter & now there the script which you have to embed on the page you need to track social integration


