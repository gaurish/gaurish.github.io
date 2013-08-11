---
author: gaurish
comments: true
date: 2008-07-12 21:35:00+00:00
layout: post
slug: howto-get-inlineembedded-comment-form
title: Howto get Inline/embedded Comment form in Blogger
wordpress_id: 29
categories:
- Blogging
- Guides and Howtos
- site related
---

Most people don't like the default comment style of blogger, which is to have comments in separate window with a diffrent theme which does not match your site. for this reason alone people switch to other blogging platform like wordpress which have this features since ages.  
  
  
  
Now blogger team has came to rescue, added inline comments, so that your readers can comment right on the page.however this feature is in testing phase only as it has lot of bugs.  
  
but this does not mean you should not try it.  
  
  
  
I have successfully implemented this on my blog, and shall guide you to do that same  
  
  
  
1) Open http://draft.blogger.com/ & sign in with your user id & password  
  
  
  
2) Upon reaching Dashboard, Navigate to Settings  
  
[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SHkc9f8W3SI/AAAAAAAAAMc/aiPuEYaAcf0/s320/inline1.jpg)](http://3.bp.blogspot.com/_wMAC6frBFdw/SHkc9f8W3SI/AAAAAAAAAMc/aiPuEYaAcf0/s1600-h/inline1.jpg)  
  
  
  
3) Under Comments Tab; select "Embedded below post" in Comment Form Placement. then click on Save Settings.  
  
[![](http://3.bp.blogspot.com/_wMAC6frBFdw/SHkexEYvxMI/AAAAAAAAAMk/V2KfsAiJcXI/s400/inline2.jpg)](http://3.bp.blogspot.com/_wMAC6frBFdw/SHkexEYvxMI/AAAAAAAAAMk/V2KfsAiJcXI/s1600-h/inline2.jpg)  
  
  
  
4) Now the Embedded comments should appear, If you have custom template, you will need to make a small changes to your template code. But don't worry, it's a small change!  
  
  
  
i) First Backup your template. to backup, navigate to Layout>Edit HTML. Under Backup / Restore Template head. Click Download Full Template.  
  
  
  
  
  
ii) Now go to Layout>Edit HTML in your blog's dashboard and check the "Expand widget templates" box.Search for this line in template code:  
  
_  
  
_  
  
_< b:include data='post' name='comments'/>_  
  
**now just after this add line**  
  
_< b:include data='post' name='comment-form'/>_  
  
  
  
please note, the above line needs to be added without deleting other line. it should be added just below it   
  
  
  
  
  
If you have done all above things correctly then you should see an embedded comment form. if not then please re-read the above and verify that you did everything correctly. if you still not get it then you can ask but do give me all details. like your blog url,template,what procedure did you take etc etc.  
  
  
  
This is a welcome feature on blogger which would stop many users from migrating to other blogging platforms.  i hope blogger team fixed all current issues and makes it LIVE soon.  
  
  
  
Please feel free to comment on this post & test the new feature before implementing it on your blog. you can learn about embedded comment forum on [Bloggerindraft blog](http://bloggerindraft.blogspot.com/2008/06/new-feature-embedded-comment-form.html)

Did you enjoy this Post?.Please give your feedback at contact at gaurishsharma.com.
Read more at GaurishSharma.com
