---
author: gaurish
comments: true
date: 2010-06-03 13:34:32+00:00
layout: post
slug: direct-server-data-transfer-ftp-recursive
title: '[Howto] Direct Server site transfer via FTP(recursive)'
wordpress_id: 418
categories:
- Guides and Howtos
- Internet
---

[![Internet-Globe](http://www.gaurishsharma.com/wp-content/uploads/2010/06/wglobe-150x150.jpg)](http://www.gaurishsharma.com/wp-content/uploads/2010/06/wglobe.jpg)Recently, I faced a situation whiling moving fairly large image sharing website from shared hosting to a dedicated as it was taking too much resources. there were few challenges in this site transfer:



	
  * Number of images were over 90,000 and size of about 95GB which rules of conventional method of first downloading everything from old server  on your own machine and then uploading to new server is not feasible.

	
  * Shared hosting provider only gave FTP access. so it rules out rsync,scp,bittorrent or anything similar based transfers. host even refused to achieve the 90,000 files.


In short, you will have to move all files and database via FTP.  Here is how:<!-- more -->


### Get the Database Dump:





	
  1. Download [SQLBuddy](http://www.sqlbuddy.com/download/), extract it & upload it to your old server via FTP. [Download Link](http://www.sqlbuddy.com/download/)

	
  2. Now open webbroswer, Now goto the localisation where you extracted it. For example, location for me was http://gaurishsharma.com/sqlbuddy(this is no longer accessible). yours might be similar.

	
  3. Login with your username and password.Click on **Export **and follow on screen instruction. now a database dump file *.SQL will be create in _../sqlbuddy/exports/export.sql_. Which you can use to restore database.




### Moving All Files





	
  1. Login to your new server via shell account.

	
  2. For transfer we will use wget - which is available on all linux based servers. we will use the following command



    
    wget -r -c -nH -l0 ftp://USERNAME:PASSWORD@ftp.domain.com/ --append-output=websitedownload-wget.log -b


Where:

USERNAME: username of old server
PASSWORD: actual password of old server
ftp.domain.com: is the URL or IP address of your old FTP server

Now, after you run its command. you get a output like this

Continuing in background, pid 16554.

-jailshell-3.2$

This means that wget is now downloading all the files from your old server in background, so you can go for sleep and check back. to check the process you can read logfile _websitedownload-wget.log_


### **Explanation of Options**


-r flag: recursively download all files and directories.
-c flag: not re-download everything that’s already been downloaded (and continue everything that’s been half done).
-nH flag: to make wget not create a directory with the name of the host prior to fetching the files.
-l0 flag: to make sure wget goes down every directory and downloads. By default, wget only goes down 4 directories.
--append-output: it will save the entire download output to file, so you can read it later.
-b flag: it will run wget into background so you can close the terminal and the transfer will still be running.

I Personally tried this method and it works great! The biggest advantage of wget method is that incase transfer gets interrupted or the server goes down,can you can 'resume' from where you left.

Hope this help you when you are moving large websites
