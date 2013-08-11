---
author: gaurish
comments: true
date: 2012-02-03 12:04:33+00:00
layout: post
slug: how-to-fully-disable-caching-in-drupal-7
title: How-To Fully Disable Caching in Drupal 7
wordpress_id: 667
---

Caching helps to cut the load on server & increase server speed. Hence, Drupal comes with caching build-in at various levels. there will be situations where,  you may want to disable *ALL* caching like I was doing some module development and without clearing out the caches the changes were not visible. So, I had to disable caches.  Incase, you too want to disable Caching for say for development - here below



	
  1. Go to _Site Configuration_ -> _Performance_:

	
    * Set the following options, and click _Save configuration_:

	
      * **Caching mode:** Disabled

	
      * **Minimum cache lifetime:** none

	
      * **Page compression:** Disabled

	
      * **Block cache:** Disabled

	
      * **Optimize CSS files:** Disabled

	
      * **Optimize JavaScript files:** Disabled




	
    * Click _Clear cached data_.




	
  2. Go to _Site building_ -> _Views_ -> _Tools_:

	
    * Check _Disable views data caching_ and click _Save configuration_.

	
    * Click _Clear Views' cache_.




	
  3. Install the [Devel module](http://drupal.org/project/devel), and go to _Site Configuration_ -> _Devel settings_:

	
    * Check _Rebuild the theme registry on every page load_ and click _Save configuration_.




	
  4. Add the following to your .module file to disable menu caching


[php]

function hook_init(){
   //FIXME: remove before going into production
   menu_rebuild();
}[/php]

With this, now ALL caching in drupal will disabled. Enjoy quicker development & don't forget to undo these changes once your site goes into production!
