---
author: gaurish
comments: true
date: 2011-02-24 12:24:12+00:00
layout: post
slug: fix-microsoft-security-essentials-version2-install-upgrade-fails-error-code-0x75633fbf
title: '[Fix] Microsoft security essentials version2 install & upgrade fails, Error
  code: 0x75633fbf'
wordpress_id: 548
categories:
- Windows
tags:
- error
- guide
- Microsoft
---

Trying to upgrade or install Microsoft security essentials Version 2 an it fails with the following error


> **The instruction at 0x75ef3fbf referenced memory at 0x00xxxxx. The Memory could not be read**


And the error dialogs looks similar to ones given below? Then Read on on how to fix this:



[caption id="attachment_549" align="aligncenter" width="570" caption="Error While Upgrading to Version 2"][![Microsoft Security Essentials Version 2 Upgrade Error dialog ](http://www.gaurishsharma.com/wp-content/uploads/2011/02/mse-v2_upgrade_error_memory_could_not_be_read.png)](http://www.gaurishsharma.com/wp-content/uploads/2011/02/mse-v2_upgrade_error_memory_could_not_be_read.png)[/caption]

[caption id="attachment_550" align="aligncenter" width="300" caption="Same error, when trying to install a fresh copy MSE v2"][![Microsoft Security Essentials version 2 installation error dialog ](http://www.gaurishsharma.com/wp-content/uploads/2011/02/mse-v2_error_memory_could_not_be_read-300x191.png)](http://www.gaurishsharma.com/wp-content/uploads/2011/02/mse-v2_error_memory_could_not_be_read.png)[/caption]




## The Problem Explained


This issue may have been caused as some of Microsoft Security Essentials (Version 1) files would have got corrupted during the upgrade process on your computer or some for worse, some important system files need by windows have have been effected. In my case,  <!-- more -->I received an error message while trying to upgrade Microsoft Security Essentials to the latest version on my Windows 7 Ultimate based computer. you will also get the same error if you first uninstall Microsoft Security Essentials (Version 1) from Add/Remove Programs and try to install Microsoft Security Essentials (Version 2). This was weird error message that I have not seen before. Clueless on what this particular error message meant, I searched via google using the error code 0x75ef3fbf as keyword. found nothing, then search a bit more using "Microsoft Security Essentials Upgrade Errror". found hundreds of people were facing difficulty in upgrading to version 2 but its my back luck, the error I got(0x75ef3fbf) is unique error & nobody else apart from myself got that error. so contacted Microsoft Techical Support team by submitting a support case and they helped me fix this error. I am happy to report that after trying to this issue from past 15days, this issue is **SOLVED!**


## Step-by-Step Guide on how to fix




**Step 1** :- Uninstall the traces of Microsoft Security Essentials which was partially installed during the upgrade.

**Step 2** :- Run Scan to verify integrity of all system files



**Step 3** :- Reinstall Microsoft Security Essentials.

_Note: Please try the following steps in the same order as provided above. If Step 1 did not work, please proceed to the next step. Please note down any error messages or notable changes you find as you try the steps. Post them in comments, I will try to help you_


### Troubleshooting Steps




#### **Step 1:**





	
  * [Download](http://gaurishsharma.com/downloads/mssefullinstall-x86fre-en-us-vista-win7.exe) MSE v1 installer from [here](http://gaurishsharma.com/downloads/mssefullinstall-x86fre-en-us-vista-win7.exe).

	
  * Save the file to your Desktop.




#### **Step 2:**





	
  * To open Command Prompt console: 

**FOR XP**: Click Start -> RUN -> type CMD in the Run Window and then hit enter.

F**OR Vista and W7**: Click Start -> All Programs -> Accessories -> Right click on Command Prompt and select "**Run as Administrator**".

	
  * In the Command Prompt console type: _CD %USERPROFILE%\Desktop_ <-hit **ENTER**Note: Do not forget the space between CD and the % sign.

	
  * 5. Type: mse <-then hit the TAB button.

	
  * 6. Depending on your Operating System, after hitting tab it should either appear as any of the three below:mssefullinstall-x86fre-en-us-vista-win7.exe

	
  * 7. Now put a space in between the whole line and put /U as seen below:mssefullinstall-x86fre-en-us-vista-win7.exe /u

	
  * 8. Hit ENTER and this should uninstall Microsoft Security Essentials.




#### Step 3


There is a strong chance that important system files might have been corrupted. so its best to run System File Check(sfc). here how to do this



	
  * Open Command Prompt. as said in Ste 2Important: You must run Command Prompt as an administrator in Windows 7 and Windows Vista to use System File Checker.

	
  * type the following command and then press Enter.sfc /scannowNote: There's a space between sfc and /scannow.

Scan will take few minutes to complete and after a while. If there were some files corrupt, you will get this kind of message:



[caption id="attachment_551" align="aligncenter" width="300" caption="Example SFC screen shows that there are corrupt system files"][![Example SFC screen shows that there are corrupt system files](http://www.gaurishsharma.com/wp-content/uploads/2011/02/sfc_error-300x148.jpg)](http://www.gaurishsharma.com/wp-content/uploads/2011/02/sfc_error.jpg)[/caption]
	
  * If you get this similar message, then please reboot your computer.




#### Step 4


Now, we have removed all traced of MSE v1 and also repaired system files using sfc scannow command. lets try and install MSE v2



	
  * [Download](http://www.microsoft.com/security_essentials) Latest version of Microsoft security essentials from Microsoft

	
  * Try to install it as you normally would by running the installer and clicking next,next few times


If you followed everything correctly, then this time MSE verion 2 should install normally without any error. it took me and entire Microsoft support team 15days to find a solution but I am posting it here, so you guys don't have to suffer.

Happy Fun and keep using this excellent Free Antivirus from Microsoft!
