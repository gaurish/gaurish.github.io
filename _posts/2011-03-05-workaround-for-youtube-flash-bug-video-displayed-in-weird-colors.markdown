---
author: gaurish
comments: true
date: 2011-03-05 09:02:23+00:00
layout: post
slug: workaround-for-youtube-flash-bug-video-displayed-in-weird-colors
title: Workaround for Youtube Flash Bug | Video displayed in weird colors
wordpress_id: 561
categories:
- Internet
- Linux
- Windows
tags:
- flash
- youtube
---

With Recent Flash upgrade to version 10.2, I faced a a strange issue with regarding to playing videos on youtube. all video I played on main site or yourtube video embedded in other sites like facebook were in red color, while the audio was playing just fine. something like in screenshot below:

[caption id="attachment_562" align="aligncenter" width="300" caption="Youtube showing red color video due to Flash"][![Youtube showing red color video due to Flash](http://www.gaurishsharma.com/wp-content/uploads/2011/03/youtube_video_bug_red_color-300x246.png)](http://www.gaurishsharma.com/wp-content/uploads/2011/03/youtube_video_bug_red_color.png)[/caption]

It turns out that this is a bug in Adobe Flash Player 10.2 introduced because adobe enabled hardware acceleration to for all users, but in case hw accel does not work properly. video will appear in weird colors. while adbobe is working on the bugfix, the current workaround is to **disable Hardware acceleration. **


## **WorkAround:**





	
  1. Goto **[http://www.youtube.com/swf_test.html<!-- more -->](http://www.youtube.com/swf_test.html)**

	
  2. Click on **Settings** & Uncheck/Clear "**Enable Hardware Acceleration"**![](http://www.gaurishsharma.com/wp-content/uploads/2011/03/Screenshot-YouTube-SWF-Testing-Google-Chrome-300x229.png)

[caption id="attachment_566" align="aligncenter" width="300" caption="Disable hardware acceleration"][![Flash Player - Disable hardware acceleration](http://www.gaurishsharma.com/wp-content/uploads/2011/03/Screenshot-YouTube-SWF-Testing-Google-Chrome-1-300x229.png)](http://www.gaurishsharma.com/wp-content/uploads/2011/03/Screenshot-YouTube-SWF-Testing-Google-Chrome.png)[/caption]

	
  3. Close all tabs & Restart your Browser.


Everything should be fixed now, if not; then you will have to downgrade to previous version of browser.


### Further Reading: [Video not displaying (black box over player) or cannot seek/scrub (weird or no scroll bar) | Youtube Support Forums](http://www.google.com/support/forum/p/youtube/thread?hl=en&tid=782d433caef8ec2b)
