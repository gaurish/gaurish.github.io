---
author: gaurish
comments: true
date: 2010-01-28 18:27:50+00:00
layout: post
slug: cdrtools-vs-cdrkit-the-india-pakistan-of-cddvd-burning-toolslinux-only
title: 'cdrtools vs cdrkit: The India-Pakistan of CD/DVD burning tools(Linux Only)'
wordpress_id: 382
categories:
- Archlinux
- Editorial
- Linux
---

## **Background**


Since ages ago, [cdrtools](http://en.wikipedia.org/wiki/Cdrtools) was the default tool-set used for optical disc buring on Linux. Under the hood of those pretty GUI programs like k3b/brasero, was actually cdrtools which did the dirty work.it was being actively developed by a team led by [Joerg Schilling](http://en.wikipedia.org/wiki/Jörg_Schilling).The whole code was licensed under GPL.

One fine Morning,

Mr. Schilling decided to change license to [CDDL](http://en.wikipedia.org/wiki/Common_Development_and_Distribution_License).This is where everything started to go wrong!


## **What is the issue?**


CDDL license is incompatible with the GPL.The CDDL is intended to be GPL incompatibleso cannot be distributed along with GPL code. Hence, it became illegal for Linux Distributions to redistribute cdrtools.



## **Debian comes to rescue!**


Linux didn't have any alternative to cdrtools, hence [debian project decided to fork last available GPLed code into Cdrkit](http://lists.debian.org/debian-devel-announce/2006/09/msg00002.html). they dropped cdrtools and included cdrkit. every major distro like Fedora,Ubuntu,Mandriva supported debian and did the same.debian took the responsibility and start to maintain cdrkit.


## Cool, everything finally settled.


No, there is one small problem.CD/DVD burning is a complicated business that needs a lot of knowledge and also requires a lot of development effort which debian does not have.lately, it has been seen cdrkit  is not been actively developed (current to last stable was around a year).Addionatlly it is technically inferior to cdrtools.cdrkit still does not generate proper iso-level-3 file systems and has trouble with big file support(the famous 4.3GB data limit in DVD against the real capacity of 4.7GB) .
This is the reason creation of proper blu-ray in linux is so hard.
it seems the developers of cdrkit don't have the resources/skills to maintain such a complex software.



## **Guess, we are stuck!**


So Choice is what we have in this.If you face problems with cdrkit, there are two options:

1) Built and Install Cdrtools yourself.Source is available at its [Home Page](http://cdrecord.berlios.de/old/private/cdrecord.html). ArchLinux users can get it on aur.

2) (Last Option)Switch to propertiery closed source burning suite:[NeroLinux.](http://www.nero.com/ena/linux4.html). if everything fails then only you should go by this route. I would strongly advise you to try choose option 1)

**What is the purpose of this post**
The purpose of this post if to let the users know the actual situation/state of CD/DVD burning apps in Linux. And let them select which software they want to use.
