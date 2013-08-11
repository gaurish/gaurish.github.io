---
author: gaurish
comments: true
date: 2008-09-20 12:53:00+00:00
layout: post
slug: archlinux-stop-dhcp-from-overwriting
title: 'ArchLinux: Stop dhcp from overwriting resolv.conf(Linux Only)'
wordpress_id: 45
categories:
- Archlinux
- Linux
---

Here is a Quick tip for people using Archlinux:   



[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SNTsFOH2RWI/AAAAAAAAAS8/Xd9QsFEehaQ/s200-R/archlinux.png)](http://1.bp.blogspot.com/_wMAC6frBFdw/SNTsFOH2RWI/AAAAAAAAAS8/KG78eoy8Uts/s1600-h/archlinux.png)

  

Sometimes we don't want dhcpcd overwriting our resolv.conf anymore, since it is customized. We do, however, want dhcpcd to continue to automatically set out IP, default gateway, et cetera. To cause this effect we will edit `/etc/conf.d/dhcpcd` as root, with our favorite editor. The directive we are looking for is `DHCPCD_ARGS` and by default that directive should look like the following figure:    


    
     
{% highlight sh %}
> DHCPCD_ARGS="-t 30 -h $HOSTNAME"
{% endhighlight %}

To that directive, add the -R flag. Your directive line should look something like the following figure:   


{% highlight sh %}
> DHCPCD_ARGS="-t 30 -h $HOSTNAME -R"
{% endhighlight %}

Taken from [Archwiki](http://wiki.archlinux.org/index.php/Post_Installation_Tips)
