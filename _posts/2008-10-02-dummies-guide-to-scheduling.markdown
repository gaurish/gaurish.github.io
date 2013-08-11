---
author: gaurish
comments: true
date: 2008-10-02 17:41:00+00:00
layout: post
slug: dummies-guide-to-scheduling
title: Dummies Guide to Scheduling Downloads(Linux Version)
wordpress_id: 51
categories:
- Bsnl Broadband
- Guides and Howtos
- Linux
---

[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SOUABh3ZuBI/AAAAAAAAAWw/X0FgKa48o0U/s200-R/3810-linux-logo.jpg)](http://3.bp.blogspot.com/_wMAC6frBFdw/SOUABh3ZuBI/AAAAAAAAAWw/iRu3TE2iwg4/s1600-h/3810-linux-logo.jpg)

Linux is a stable OpenSource Operating system.It has a ability to run for long hours and crashes are rarely seen.On top of it, it has a inbuilt scheduler which is robust and it never misses tasks. All this Characteristics make Linux a perfect choice for downloading. Yeah almost perfect choice (discussed later).  

In This Guide we would learn how to smartly schedule downloads. This way files would be automatically downloaded while you sleep. This Guide is mainly for BSNL/MTNL broadband subscribers. I have Tried to prescribe a general procedure which is applicable on all major Distributions.so distribution specific goodies are not discussed here.  

  

Mainly there are two mode of this, you need to pick a method which applies to you.  



  * **Router Reboot method**: Suitable when your connection is configured as always-on and router is PPPoE mode. so you don't need to dial your connection every time you connect to Internet. it works with selected routers which supports telnet connectivity.Dependant upon routers.  




  * **Bridge Mode:** Suitable when you dial to connect to Internet using a Dialer program on your PC. in this setting your PC is in Bridge mode.it works with every router.  



  

  



**Understanding Cron** **Daemon**  

Before we begin we should know how about cron - default linux scheduler   

Cron Daemon is a default scheduler for Linux based systems.Cron Daemon is responsible for scanning the crontab files and running the commands at the appropriate time. It always runs in background, wakes up every minute to check for any scheduled taks pending for execution. then it executes them and goes back to sleep.   

  

Crond reads tasks from crontab, anything you write in your crontab with proper syntax will be read & excuted by crond. Crontab as name suggests, is basically a file where sheduled tasks are arranged in tabular forum.The syntax of crontab is fairly simple.  






Minutes Hours Day Month Day of the month command  


enter the minutes part of time, legal values 0-60
Enter the hours, in 24hr format. legal values 0-24
Enter the Day number starting from Monday, legal values 0-7
Enter the month,legal values 1-12
Enter a Date, legal values 1-31
Command you want to execute at scheduled time
 
  

  

  

  

use command "visudo" to edit crontab.it would load a editor depending upon your $EDITOR variable. on Ubuntu you would get nano  

[how to use nano](http://www.gentoo.org/doc/en/nano-basics-guide.xml)(easy)  

[how to use vi](http://mirror1.linuxcbt.com/demos/classic_edition/LinuxCBT_Classic_vi.html) (advanced)  

  

**Things Which are common among both methods  

  

**1) Create a simple text file in your home folder and name it **"downloads.txt**" & notedown its full path. Insert the *Direct* links of files you want to download into this newly created file. The files given in this would be downloaded by wget automactically.wget can handle http & ftp downloads. After download completes remove the link and enter new ones. insert one link per line. Remember to add direct link only.  

  

2) If you use torrents, install your torrent client and notedown its full path to its binary. you can use "whereis" command to find its exact location. generally its /usr/share/sbin. If you are looking for worthy torrent clients, look for [deluge](http://deluge-torrent.org/) or azurus now vuze  

  



**Router Reboot Method**

1) I wrote a simple Shell script for rebooting router. it works nicely on D-link GLB 502T. although you may need to change userid,password & command values.copy paste this script in a file and save it as _router-reboot.sh_. make it excutable by   

  
{% highlight sh %}
chmod a+x router-reboot.sh
{% endhighlight %}
  

  


{% highlight sh %}
    #!/bin/sh
    #############################################
    #Script Written By Gaurish Sharma
    #change the password,userid & command values with your own set
    #the default password & username
    # in most cased is 'admin'
    #use it in terminal as sh router-reboot.sh | telnet
    #(C) GaurishSharma.com
    #############################################
    add='open 192.168.1.1'
    userid='root'
    password='your_passoword'
    command='reboot'
    echo $add
    sleep 1
    echo $userid
    sleep 1
    echo $password
    sleep 1
    echo $command
    sleep 1
{% endhighlight %}
  

2) Open Terminal and enter "crontab -e". enter the following in your crontab and save it  


{% highlight sh %}
    # m h  dom mon dow   command
    # Reboot Entry, please replace with correct path
    10 2 * * * cd /home/gaurish/scripts && sh router-reboot.sh | telnet
    # Start Torrent client, please replace with correct path of your router
    12 2 * * * DISPLAY=:0.0 /opt/azureus/azureus
    # Downloads via wget, Please replace with corrent path
    13 2 * * * wget -ci /home/gaurish/downloads.txt
    # Reboot Entry, please replace with correct path
    50 7 * * * cd /home/gaurish/scripts && sh router-reboot.sh | telnet
{% endhighlight %}

  

3) Now we need to enter command to shutdown computer everyday at 7.51AM.this only can be done via root user. so now the enter command as "sudo crontab -e" and Insert this line.  


{% highlight sh %}
    50 7 * * * /sbin/shutdown -h 0
{% endhighlight %}

  

4) (Optional) you can install mailx package to see the log of what happened while you were sleeping  

  

  



**Bridge Mode**

1) we would be using default command which you use to dial to internet. on most cases its pon dsl-provider for connectinig and poff for disconnection . in case the command are diffrent on your machine please replace them.  

  

2) Open Terminal and enter `crontab -e` now paste the following in it  


{% highlight sh %}
    # m h  dom mon dow   command
    # Start Torrent client, please replace with correct path of your torrent program
    10 2 * * * DISPLAY=:0.0 /opt/azureus/azureus
    # please replace with correct path of download.txt
    13 2 * * * wget -ci /home/gaurish/downloads.txt
{% endhighlight %}
  

3) Now we need to use root crontab, use `sudo crontab -e` to access it.  


{% highlight sh %}
    10 2 * * *  /usr/bin/pon dsl-provider
    49 7 * * * /usr/bin/poff
    50 7 * * * /sbin/shutdown -h 0
{% endhighlight %}

  

4) (Optional) you can install mailx package to see the log of what happened while you were sleeping.

  

  

**What you are missing in Linux, comparing to windows?**  

In starting of this post i said, ** **almost perfect choice for downloading. so you gotta missing something. which is ability to power on your PC automatically.  

I am still searching for a method to start a Linux box automatically at a specific time.   

As a workaround you can do the same thing via your BIOS, but a limited no of BIOS support this. so either leave your machine running with monitor turn off or use the BIOS trick.  

  

**Related Posts:**   



  * [Dummies Guide to Scheduling Downloads(Windows)](http://www.gaurishsharma.com/2008/09/dummies-guide-to-scheduling-downloads.html)


  * [Solution:Some Random sites do not open with BSNL Broadband](http://www.gaurishsharma.com/2008/08/solutionsome-random-sites-do-not-open.html)
