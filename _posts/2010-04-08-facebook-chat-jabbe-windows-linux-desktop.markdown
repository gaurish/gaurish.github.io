---
author: gaurish
comments: true
date: 2010-04-08 17:50:23+00:00
layout: post
slug: facebook-chat-jabbe-windows-linux-desktop
title: Run Facebook Chat directly from Desktop(New method)
wordpress_id: 396
categories:
- Guides and Howtos
- Internet
tags:
- chat
- facebook
---

Ever wanted to use Facebook chat without logging into Facebook website? Looking are a Desktop application for Facebook chat? Do you hate Facebook chat because it makes your browser go crazy ? If answer is "**Yes**" then Read On...

[Recently](http://developers.facebook.com/news.php?blog=1&story=361), Facebook has enabled support for XMPP/Jabber protocol which means that now you can using standalone Instant Messengers like Pidgin(Works on Windows,Mac & Linux),[iChat](http://www.apple.com/macosx/what-is-macosx/ichat.html)(Mac only).  This works on Windows,Linux and Mac on any application that support jabber protocol.

here I would demonstrate to do this on Windows with pidgin.<!-- more -->

**Step 1)** Set your Facebook username by going [here](http://www.facebook.com/username/). if your profile url is facebook.com/xxxxx then xxxxx will be your username. please remember it, we will need in later steps.

[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/get-fb-username-1024x257.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/get-fb-username.png)

**Step 2)** [Download & install Pidgin](http://pidgin.im): Pidgin is Open Source IM App which can be freely downloaded from [Pidgin.im](http://www.pidgin.im/). Please visit the site and [download](http://www.pidgin.im/) & Install. Installation is pretty straightforward - typical windows style. Just keep Clicking Next,Next,Next and pidgin would be install automatically.


[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-install-step1-150x150.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-install-step1.png)


**Strep 3)** Configuration: now Launch Pidgin. you will be greeted with Account Dialog Box  click on "**Add Account**" to a facebook account

[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addcount-1-alt-150x150.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addcount-1-alt.png)**Step 4)** Now in Add Account Screen, enter the following & leave rest to default:

[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addaccount-2.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addaccount-2.png)



	
  * protocol: XMPP

	
  * username: your facebook username . Its the same which you get in step-1

	
  * Domain: chat.facebook.com

	
  * password: <_enter your facebook password_>

	
  * Check Remember Password


**Step 5)** In the Advanced Tab, Do the following

[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addaccount-3.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-addaccount-3.png)



	
  * Uncheck "_Require SSL/TLS_"

	
  * Check "_Allow plaintext auth over unencrypted streams_"

	
  * Connect port: 5222

	
  * Connect Server: _chat.facebook.com _


**Step 6**) Click on Save and wait for few seconds while pidgin connects to facebook. If you have configured the settings correctly then you should be able to see this:

[![](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-contactlist-final.png)](http://www.gaurishsharma.com/wp-content/uploads/2010/04/pidgin-contactlist-final.png)

Congrats! you can start chatting with your friends rightway

**Bonus Tip:**Pidgin supports multiple protocols. so you can also add your GTalk,Yahoo Messenger or MSN accounts same way you added your Facebook account and chat on all of them at the same time. no need to install separate client program for each protocols.  Great Nice eh?
