---
author: gaurish
comments: true
date: 2009-01-22 21:36:10+00:00
layout: post
slug: migrating-from-blogger-to-selfhosted-wordpress
title: Migrating from Blogger to selfhosted Wordpress
wordpress_id: 75
categories:
- Blogging
- Guides and Howtos
tags:
- blogger
- Blogging
- migration
- switch
- wordpress
---

Google's blogger software for blogging is easy to use and effective. But the major drawback is that, blogger is not fully flexible to suit everyone needs, it does not support additional static  pages. In short, with blogger you can't have full control over your blog. this is where wordpress scores the most. Being of  Open Source nature, you can modify it to your needs & extend its functionality further with help of plug-ins.

I myself have migrated to a self-hosted wordpress driven blog and would share my experience; the most seamless way to make the switch.

Please Note: As i was running blogger with a custom domain(_gaurishsharma.com_) so switch was relatively easier for me, as i didn't have to use any dirty scripts to redirect traffic from old blogger blog to new wordpress blog.
**
**


## ** Aims of this Guide:**





	
  1. Move all the posts and comments data from old blogger blog to your new wordpress blog.

	
  2. Maintain the permalinks of your old blog, so links from search engines and bookmarks don't get broken in process.Thereby maintaining backlinks for a good Page Rank

	
  3. Carry Over your RSS feed subscribers to new blog.

	
  4. Making the switch as seamless as possible with least amount of downtime possible.




## **Assumptions while making this guide:**





	
  * You use feedburner service, for feed syndication

	
  * you are publishing your blog on a custom domain(eg. yourname.com) and if you are still stuck on sub-domain of blogspot(like xxx.blopspot.com) its time to take the plunge, go register your own domain(yourname.com).A custom domain helps build a unique online identity and shows that you are really serious about blogging.  these days Domain are really affordable around Rs.350INR per year.




## **The Procedure Explained, Step-by-step:**





	
  1. **Moving to custom domain:** If you are publishing on subdomain of blogspot(xxx.blogspot.com). First step is switch to a custom domain, instrutions can be found on [Google Help page](http://help.blogger.com/bin/answer.py?hl=en&answer=55373).After changing to a new address, kindle wait for atleast 3-6months, so all traffic from your old blog's URL its automatically your new custom domain. I realize 3months is a long period but its necessary  for making a smooth switch, but if you are less patient then try this hack.

	
  2. **Importing Data**: Since, all of your traffic is coming to your new custom domain(yourname.com). its time make a switch. Go to Wordpress.com and sign-up for a free blog. choose whatever address you like as that's gonna be temp. Now, Import data from your blogger blog by logging into wordpress dashboard & Tools --> Import --> Blogger.Next authorize wordpress to access your blogger blog and press magic Import Button. importing post would take some time. so please be patient.after importing completes, set the author name.![acces_authroise](http://www.gaurishsharma.com/wp-content/uploads/2009/01/4-grant-access-blogger-google-account-1-600x322-300x161.png)![2-import-data-from-blogger-into-wordpress](http://www.gaurishsharma.com/wp-content/uploads/2009/01/2-import-data-from-blogger-into-wordpress-300x80.png)

	
  3. **Exporting Data**: Now navigate to Tools --> Export.Save this file to your computer.now all your posts & comment are saved on your computer disk. at this point we no longer require that free wordpress blog we registered in step 2

	
  4. **Installing Wordpress**:Login to your webmaster's Control Panel. most webhost have Cpanel installed which has Fantastico feature, with its help you can install wordpress in few clicks. else you could The famous manual install, the only extra step in manual method is database creation by phpadmin.

	
  5. **Importing final data**: Login into your newly installed wordpress's dashboard. Goto Tools --> Import > Wordpress. broswe to the location of file which you saved in step-3.

	
  6. **Maintaining Permalinks**: Now we need to use the exact URL stucture as we had in our blogger blog. First Install plugin called - [Maintain Blogger Permalinks](http://justinsomnia.org/files/wp-maintain-blogger-permalinks-1.0.zip) by uploading this to your_ wp-content/plugins/_ dir. Activate the plugin once and run it via _Tools > Permalinks_. This is one time task and you can safely remove this plugin afterwards.

	
  7. Next go to _Settings --> Permalinks --> Custom_ & enter the following stucture:- _/%year%/%monthnum%/%postname%.html_

	
  8. Importing feed: Login to your feedburner account. and click on Edit Feed Details. In feed url enter _http://www.your-domain-name-here.com/feed/rss_ eg. http://www.gaurishsharma.com/feed/rss


Thats all.
Now you change update NS records of your domain, to redict visitor to your new wordpress blog. Remember: It takes about 24-48 in Dns propagation.

Happy Blogging
