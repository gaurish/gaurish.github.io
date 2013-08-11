---
author: gaurish
comments: true
date: 2008-11-14 09:07:00+00:00
layout: post
slug: linux-ext3-partition-detected
title: '[Linux] Ext3 partition detected wrongfully as ext4'
wordpress_id: 57
categories:
- Linux
- Myself and My Life
---

**Oh No!**

[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SR0-_ti38FI/AAAAAAAAAZQ/Dl-43NTRwRg/s200/Homer+Simpson+Oh+No.jpg)](http://1.bp.blogspot.com/_wMAC6frBFdw/SR0-_ti38FI/AAAAAAAAAZQ/Dl-43NTRwRg/s1600-h/Homer+Simpson+Oh+No.jpg)

  

  

Recently, A partition on my backup harddrive was corrupted. It was i was clueless how it had happened. further, now the partition was refusing to mount and it was being detected as ext4.  

I tried mounting is manually:  


    
    gaurish  ~  $   sudo mount /dev/sdb6 /media/fl/
    mount: unknown filesystem type 'ext4'

  

  

Dmesg said  

  

"_EXT3-fs: sdb6: couldn't mount because of unsupported optional features (ca9bc1e0)_."  

  

I was not sure what to do next  

So i cried for help on various online Forums[[1](http://bbs.archlinux.org/viewtopic.php?id=56975)][[2](http://www.linuxquestions.org/questions/linux-newbie-8/sos-a-partition-on-backup-drive-cant-be-mounted-detected-as-ext4-676708/)][[3](http://www.thinkdigit.com/forum/showthread.php?t=99748)] but all in waste.  

After that i got pissed off and decided to take matter into my own hands and starting reading on how Partitions in linux are made etc. Then i came to know about superblock.  

Bingo!, i had a bad [superblock](http://en.wikipedia.org/wiki/Superblock).  

Here is a Quick Procedure to recover from a bad super block(read nightmare)  

Open Terminal and type the following commands:  

1) see  backup superblock location  

``  



> `~  $ dumpe2fs /dev/sdb6 | grep -i superblock  

  

  

Output:  

dumpe2fs 1.41.3 (12-Oct-2008)                                                                                                                   

Primary superblock at 0, Group descriptors at 1-2                                                                                             

Backup superblock at 32768, Group descriptors at 32769-32770                                                                                  

Backup superblock at 98304, Group descriptors at 98305-98306                                                                                  

Backup superblock at 163840, Group descriptors at 163841-163842  

Backup superblock at 229376, Group descriptors at 229377-229378  

Backup superblock at 294912, Group descriptors at 294913-294914  

Backup superblock at 819200, Group descriptors at 819201-819202  

Backup superblock at 884736, Group descriptors at 884737-884738  

Backup superblock at 1605632, Group descriptors at 1605633-1605634  

Backup superblock at 2654208, Group descriptors at 2654209-2654210  

Backup superblock at 4096000, Group descriptors at 4096001-4096002  

`

  

2) Run Fsck with Alternative Superblock  



> $   sudo fsck -b 32768 /dev/sdb6  

fsck 1.41.3 (12-Oct-2008)  

e2fsck 1.41.3 (12-Oct-2008)  

/dev/sdb6 was not cleanly unmounted, check forced.  

Pass 1: Checking inodes, blocks, and sizes  

Pass 2: Checking directory structure  

Pass 3: Checking directory connectivity  

Pass 4: Checking reference counts  

Pass 5: Checking group summary information  

Free blocks count wrong for group #12 (30380, counted=30381).  

Fix? yes  

  

Free blocks count wrong for group #127 (15027, counted=5927).  

Fix? yes  

  

Free blocks count wrong (10539272, counted=10530173).  

Fix? yes  

  

Free inodes count wrong for group #116 (32732, counted=32729).  

Fix? yes  

  

Free inodes count wrong (24812957, counted=24812954).  

Fix? yes  

  

  

/dev/sdb6: ***** FILE SYSTEM WAS MODIFIED *****  

/dev/sdb6: 934/24813888 files (6.2% non-contiguous), 14282211/24812384 blocks

  

3) Done! Partition is successfully recovered and data is safe. now we can mount it normally.  



> $   sudo mount /dev/sdb6 /media/test

Now, After this incident i have to rethink my backup strategy, which till now have been reply solely on HDDs as backup medium.   

Comment & Suggestions are welcome :)

Did you enjoy this Post?.Please give your feedback at contact at gaurishsharma.com.
Read more at GaurishSharma.com
