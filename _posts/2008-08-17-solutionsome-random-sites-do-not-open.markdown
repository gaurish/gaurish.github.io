---
author: gaurish
comments: true
date: 2008-08-17 13:56:00+00:00
layout: post
slug: solutionsome-random-sites-do-not-open
title: Solution:Some Random sites do not open with BSNL Broadband
wordpress_id: 36
categories:
- Bsnl Broadband
- Guides and Howtos
---

[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SKgokWIDuAI/AAAAAAAAAPE/fKyuRg7Q8cc/s200-R/broadband.jpg)](http://3.bp.blogspot.com/_wMAC6frBFdw/SKgokWIDuAI/AAAAAAAAAPE/z0KzAlmf2z4/s1600-h/broadband.jpg)

  

  

**BSNL Broadband** is a [broadband](http://en.wikipedia.org/wiki/Broadband_internet_access) [internet](http://en.wikipedia.org/wiki/Internet) service from state owned [BSNL](http://en.wikipedia.org/wiki/BSNL) in India. during Past few weeks many Bsnl Broadband customers are complaining that they can't open some sites like Google.com,Microsoft.com. MSN.com, Hotmail.com but can connect to mail.com,orkut.com. the sites which are not opening are random - it can be any site which does not open.If you a similar problem and can't open some sites then read on......  

There are mainly two Reasons to this Problem:-  



  * **Bad DNS**: Bsnl's DNS sometimes due to overload fails to resolve queries. sometimes this is a temporary problem. if it occurs often then change to third party DNS server like Opendns. changing DNS server is very simple process, there is no software to install. you just need to specify IP address of alternate DNS servers. Opendns also has other features like filtering of adult sites etc. detailed instructions on how to setup can be found on _[Opendns website](https://www.opendns.com/start)_. 

  



  * **Large MTU: **MTU stands for Maximum transmission Unit. it is max size of each data packet which travels across a Internet. each interface has it own MTU value. Larger MTU ensures bandwidth efficiency but it can also choke interfaces. if you have problems with your network a conservative MTU value of 1454 is recommended.to change MTU. The third party Dr. TCP software can be used to change the MTU setting. 


    1. Download this tiny utility from [here](http://www.dslreports.com/drtcp). choose exe file type  




    2. Run the utility you just downloaded.  




    3. In the **Adapter Settings**, select the Ethernet driver and adapter used to connect with BSNL broadband.  




    4. In the **MTU** box, type the 1454.  




    5. Click in any other box, without changing the data there.  




    6. Click **Save**.  




    7. Click **Exit**.  




    8. Restart the computer. 

Hopefully you be able to solve your network problems. **Enjoy High-speed enabled Internet!!**

Did you enjoy this Post?.Please give your feedback at contact at gaurishsharma.com.
Read more at GaurishSharma.com
