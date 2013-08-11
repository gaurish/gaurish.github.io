---
author: gaurish
comments: true
date: 2008-09-14 12:35:00+00:00
layout: post
slug: dummies-guide-to-scheduling-downloads
title: Dummies Guide to Scheduling Downloads
wordpress_id: 43
categories:
- Bsnl Broadband
- Guides and Howtos
---

Since state owned Bharat Sanchar Nigam Ltd (BSNL) [launched its broadband services](http://www.bsnl.co.in/newsdetailed.php?news_id=188) under the brand name DataOne through out the country on 14th January 2005 , its users have one complaint lack of unlimited plans. Due to this users were forced to download their "stuff" in odd time of 200hrs to 800hrs(IST). some smart people used to schedule download and sleep cool. others have been branded night watchman by folks around them. now lot of things have changed, speeds have in upgraded upto 2mbps and new Unlimited plans have been introduced.  

Still there are many users who still stuck with plans with data caps and Night Unlimited facility despite of Unlimited Plans being available. Mainly because of monthly rentals of data capped plans is lower and speeds are higher.  

In This post we would try to intellectually schedule our downloads. so that we can have a sound sleep while download finishes. Already their are guides available for this on Internet but this is for [Anshul Jain](http://www.orkut.co.in/Profile.aspx?uid=17865906530842121749) & [Rachit Atolia](http://www.orkut.co.in/Profile.aspx?uid=1455683984992943929) who forced me to write this post. Damn, both of you !.  



###### What you would be able to do at end of this guide?

Your computer would automatically power-on(if supported) & connect to predestined time, your download would be automatically started. And at a predetermined time your PC would turn off. Best part is that all this occur when you are in deep sleep.  



##### Requirements Tools:-

  * BSNL Internet Connection in Bridge mode(dial-up mode). Bridge mode is that when you use dialer in connect Internet. Internet is not not always on.  




  * Tested on Windows XP 32bit, may or maybe not work on Vista  




  * Any Download manager which supports scheduling, I recommend Free Download Manager(FDM). [Download FDM](http://www.freedownloadmanager.org/download.htm)  




  * Torrent Client like [utorrent](http://www.utorrent.com). required only is you regularly download via torrents, else FDM has inbuilt [bittorrent](http://en.wikipedia.org/wiki/BitTorrent_%28protocol%29) support.



##### Procedure:-

1. Click on [_Start menu_](http://upload.wikimedia.org/wikipedia/en/c/c0/StartMenuXP.png) and Open Notepad from _All Programs>Accessories>Notepad_   

2. Type the following text and save the file as `connect.bat`  

`rasdial conn_name username password`

_where:_  

Connection name have to be replaced with the name of dialer you created in xp. to find your connection name . Open_ Start menu > Control Panel > Network and Internet Connections > Network Connections. here you should find connection name. example for mine it is_  

`rasdial Bsnl jp2555355 Hari-om`  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SMz-_BlHm4I/AAAAAAAAARM/6JL7Sjs5jMU/s320-R/netowork_connection.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SMz-_BlHm4I/AAAAAAAAARM/5nI70e2LM6E/s1600-h/netowork_connection.png)

  

3. now create a similar file with following text and save it as `disconnect.bat`  

rasdial  /disconnect  

4. C<strike>reate another file similar to first two with following text and save as </strike>  

<strike>_shutdown -S -T 0_</strike>_ __**See The [Update] at end of the post**  

_  

5. Enable Hibernation by Start control > Run. type  `powercfg.cpl` and check enable hibernation. ensure there is necessary free space available.  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SMz--OopVbI/AAAAAAAAARE/WyiUPpwjYyE/s320-R/hibernate.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SMz--OopVbI/AAAAAAAAARE/ScHfdyFzenw/s1600-h/hibernate.png)

  

6.Open Scheduled tasks by tying "control scheduled" in run dialog box.  

7. Add a new schedule task by clicking on `Add schedule task`. you would be presented with Scheduled task Wizard. please click next to continue.  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_CUN7o4I/AAAAAAAAARc/-C_pGwQMTV4/s320-R/Screenshot+-+9_13_2008+,+9_02_32+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_CUN7o4I/AAAAAAAAARc/rLFMX1xOrnM/s1600-h/Screenshot+-+9_13_2008+,+9_02_32+PM.png)

  

8. Now in Select applications window, Click on Browse and navigate to the location where you have saved `connect.bat` and click on Open  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SMz_Gkc4WiI/AAAAAAAAARs/BA5wHkLo0PM/s320-R/Screenshot+-+9_13_2008+,+9_03_03+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SMz_Gkc4WiI/AAAAAAAAARs/a1lbQihhENE/s1600-h/Screenshot+-+9_13_2008+,+9_03_03+PM.png)

  



[![](http://2.bp.blogspot.com/_wMAC6frBFdw/SMz_ITBWXtI/AAAAAAAAAR0/BVd2yCweX_8/s320-R/Screenshot+-+9_13_2008+,+9_57_51+PM.png)](http://2.bp.blogspot.com/_wMAC6frBFdw/SMz_ITBWXtI/AAAAAAAAAR0/oDmGosSl49M/s1600-h/Screenshot+-+9_13_2008+,+9_57_51+PM.png)

  

9.In perform this task, select `Daily` and click on next to continue.  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_LYDXgqI/AAAAAAAAAR8/nOpEtWzyrPg/s320-R/Screenshot+-+9_13_2008+,+10_08_23+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_LYDXgqI/AAAAAAAAAR8/avpeT05FmCc/s1600-h/Screenshot+-+9_13_2008+,+10_08_23+PM.png)

  

10. In Select Time & date screen, choose Start time as 2:10 AM and Perform this task daily. Click Next to Continue.  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SM0BsILtWLI/AAAAAAAAASk/2E6nnnWZc5c/s320-R/image_1.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SM0BsILtWLI/AAAAAAAAASk/kE2NOCpMO-o/s1600-h/image_1.png)

  

11. Enter the password you use to logon, leave blank if there is no password. Click Next to Continue  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_a7QBvFI/AAAAAAAAASE/fNWuWlmuG28/s320-R/Screenshot+-+9_13_2008+,+10_19_05+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_a7QBvFI/AAAAAAAAASE/_De8cA4fpeo/s1600-h/Screenshot+-+9_13_2008+,+10_19_05+PM.png)

  

12. you will get a confirmation screen. Click on Check box `Open Advanced properties for this task when I click Finish.` and now finally click on Finish.if you didn't enter a password you get a access it denied error. please ignore and proceed to next step.  



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SMz_behZ4vI/AAAAAAAAASM/SRq1igexEwU/s320-R/Screenshot+-+9_13_2008+,+10_23_48+PM.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SMz_behZ4vI/AAAAAAAAASM/amT9U7I3A0I/s1600-h/Screenshot+-+9_13_2008+,+10_23_48+PM.png)

  

13. In Advanced properties check `Run Only If Logged on` and click Apply.  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SMz_b4wGpGI/AAAAAAAAASU/HED_TAVEf_8/s320-R/Screenshot+-+9_13_2008+,+10_25_26+PM.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SMz_b4wGpGI/AAAAAAAAASU/6jw3lvoHM0w/s1600-h/Screenshot+-+9_13_2008+,+10_25_26+PM.png)

  

14. Click on Settings tab and check `Wake computer` to run this task. Click okay  



[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_cnjWvMI/AAAAAAAAASc/gG4NqYlHmbs/s320-R/Screenshot+-+9_13_2008+,+10_30_50+PM.png)](http://3.bp.blogspot.com/_wMAC6frBFdw/SMz_cnjWvMI/AAAAAAAAASc/XpfqIYlX7SE/s1600-h/Screenshot+-+9_13_2008+,+10_30_50+PM.png)

  

15. Now you can add any other task like FDM or utorrent, in exact same procedure to be run at 2:11 AM Daily. but just choose desired program from Application Window in place of connect.bat in Step 7   

16. Now add `disconnect.bat` task to be run at 7:50 AM Daily  

17. Lastly, `Shutdown.bat` task to be run at 7:  

18. If you have done everything correctly,your scheduled task should be similar to to screenshot given below.  



[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SM0CnXXrTFI/AAAAAAAAASs/pWlqYE2_lqQ/s320-R/image_2.png)](http://4.bp.blogspot.com/_wMAC6frBFdw/SM0CnXXrTFI/AAAAAAAAASs/gQSSwDQMxuM/s1600-h/image_2.png)

  



##### How To Use

1. Set your downloads in FDM or utorrent in such a way that whenever they are started downloading begins.  

2. Put your Computer to Hibernate Mode. Hold down Shift key in Shut Down menu to see Hibernate option.  

3) Don't Turn off main AC power. if you have a UPS, please keep it on. also router needs to need on. you can turn off your monitor Only.  

  

**Congrats!, you can now sleep cool which you download "Stuff". Incase of any problems, please ask them here**  

**  

**  

**  

**  

**[Update]**  

You need a separate Utility like [Poweroff](http://www.softpedia.com/get/System/System-Miscellaneous/PowerOff.shtml) to be able to shutdown computer.  

1) Download [Poweroff](http://www.softpedia.com/get/System/System-Miscellaneous/PowerOff.shtml)  

2) Schedule to power off automatically at 7.50 AM daily.  

3) Create a Service by Service>Create Service  

4) Then Save Settings to the service  

** **
