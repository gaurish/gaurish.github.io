---
author: gaurish
comments: true
date: 2012-08-01 13:08:33+00:00
layout: post
slug: migrating-my-blog-to-appfog-cloud-initial-impressions
title: 'Migrating my Blog to AppFog Cloud: Initial Impressions'
wordpress_id: 723
categories:
- Guides and Howtos
tags:
- appfog
- cloud
- hosting
- pass
---

[AppFog Paas](http://appfog.com/products/appfog/), a cloud hosting platform launched into general availability & released their [pricing](https://console.appfog.com/pricing). Since, the pricing looks attractive, I decided to try Appfog over the weekend by migrating this wordpress blog over there. So, if you want to know how Appfog is or just want to learn how to host your wordpress blog on appfog for FREE, read on!


### What is AppFog?


AppFog is a Cloud Hosting platform which is categorized as **P**latform **a**s **a** **S**ervice(PaaS). PaaS is the thing that lets developers stay developers but still empower them to deploy applications that can reach millions.  Basically, PaaS saves you from having to do system administration & focus only on development of your web application. think of all the tasks you have to do when a new box is commissioned into production; they are silly things like installing web server,download & compile PHP/ruby, installing security update, firewall & security configuration & countless other small configurations & optimizations. With PaaS like Appfog,  you get that application environment ready out-of-the-box  & with lots of other features like scaling, cloning etc. Appfog supports multiple runtimes,  PHP(v5.3),Ruby MRI(v1.9), Java(v7), Node.js(v0.4 & v0.6), Python(v2.7) & Erlang(R14).


### Why should I care about AppFog?


Agreed, there are a lot of other PaaS solutions like Google App Engine, Redhat's OpenShift, Salesforce's Heroku, Microsoft's Azure and many others but I am going to give 2 things that according to me are special about Appfog:



	
  1. **Ability to Choose Underlying Cloud Platform & Locations:** Appfog lets you pick almost any cloud(current supported are AWS, Rackspace, Azure & HP's Openstack) with choice of location where your app would be hosted(current locations are in US,Europe & Asia). This is in sharp contract with PaaS solutions like heroku where you are forced to host in US even half of your traffic comes from other parts of the world resulting increased latency. With Appfog, you can seamlessly deploy your application to multiple clouds at different locations. Thereby reducing [SPOF](http://en.wikipedia.org/wiki/Single_point_of_failure)

	
  2. **Generous Free Quota: **[Free plan](https://console.appfog.com/pricing) gives you total 2 GB RAM(per account) which scalable over multiple instances, 1GB Database(per account), 50 GB data transfer limit(per account) & 100mb diskspace(per application). Except the 100mb diskspace, all others are pretty generous.  There is a comparison of appfog with other PaaS solutions on what you have to pay for 4 instances with 512MB each:







Pass Provider
Price/mo







dotcloud


$276






Heroku


$107






AppFog


**$0**









Based, on the two reasons given above, I set out to try Appfog by migrating this wordpress powered blog from self-managed VPS to AWS Singapore.




### The Great Wordpress Migration


creating new applications on appfog is straightforward & trivial thanks to nicely designed web console. Migrating existing apps involves few extra steps.In this part, I will describe how i got this blog running on a VPS migrated to Appfog. feel Skip this part, if you do not plan to run any PHP. However, if you plan to move your wordpress blog here, this is something you should read:



	
  1. **Download file backup & the Database dump**(.SQL file) of your blog from your existing host.

	
  2. **Install ruby**: we are going to the af command line tool to interact with appfog(reason in next section). `af` is a rubygem which needs ruby to run. Unless, you have ruby programming language already installed like me(hello there, fellow rubyist!) you need to:


	
      * On Windows: Download & install [railsinstaller](http://railsinstaller.org/)

	
      * On Linux or Mac: Use rvm.  just run the following command
{% highlight sh %}curl -L get.rvm.io | bash -s stable{% endhighlight %}

for further details, see check out the [RVM installation page](https://rvm.io/rvm/install/) or just watch the video below Once you have installed ruby, Verify ruby is correctly installed & is above version 1.9.2

{% highlight sh %}
$ ruby --version
ruby 1.9.3p194 (2012-04-20 revision 35410) [i686-linux]
{% endhighlight %}





	
  3. **Install & setup af tool**: Now, time that you open your command prompt/terminal and start typing following commands. Install af tool
{% highlight sh %}
$ gem install af
Successfully installed af-0.3.16.5
1 gem installed
Installing ri documentation for af-0.3.16.5...
Installing RDoc documentation for af-0.3.16.5...
{% endhighlight %}

login with appfog account

{% highlight sh %}
$ af login
Attempting login to [https://api.appfog.com]
Email: user@example.com
Password: ***
{% endhighlight %}

	
  4. **Configure Database details:**In Appfog, the database details are set as environment variables, so we need to edit wp-config.php and tell wordpress. basically, you need to replace staic values:

{% highlight php startinline %}
define('DB_NAME', 'db_name');
define('DB_USER', 'username');
define('DB_PASSWORD', 'password');
define('DB_HOST', 'localhost');
define('DB_PORT', 3306);
{% endhighlight %}

with the environment variables

{% highlight php startinline %}
$services_json = json_decode(getenv('VCAP_SERVICES'),true);
$mysql_config = $services_json['mysql-5.1'][0]['credentials'];
define('DB_NAME', $mysql_config['name']);
define('DB_USER', $mysql_config['user']);
define('DB_PASSWORD', $mysql_config['password']);
define('DB_HOST', $mysql_config['hostname']);
define('DB_PORT', $mysql_config['port']);
{% endhighlight %}

	
  5. **Create the app**: now, we are going to create the application & upload it on the cloud. for that first cd into the directory where you blog files are stored. for example, I have my files stored at /home/gaurish/wordpress so navigate to that director. remember, to cd into the directory & not outside the directory.{% highlight sh %}$ cd /home/gaurish/wordpress/{% endhighlight %}

next, lets create the application. the commands are self-exploratory

{% highlight sh %}
gaurish@DEN:~/wordpress$ af push
Would you like to deploy from the current directory? [Yn]: Y
Application Name: gaurishblog
Detected a PHP Application, is this correct? [Yn]: Y
Application Deployed URL [gaurishblog.aws.af.cm]: gaurishblog.aws.af.cm
Memory reservation (128M, 256M, 512M, 1G, 2G) [128M]: 512M
How many instances? [1]: 1
Bind existing services to 'gaurishblog'? [yN]: n
Create services to bind to 'gaurishblog'? [yN]: Y
1: mongodb
2: mysql
What kind of service?: 2
Specify the name of the service [mysql-7149]: mysql-gaurishblog
Create another? [yN]: n
Would you like to save this configuration? [yN]: Y
Manifest written to manifest.yml.
Creating Application: OK
Creating Service [mysql-gaurishblog]: OK
Binding Service [mysql-gaurishblog]: OK
Uploading Application:
  Checking for available resources: OK
  Packing application: OK
  Uploading (0K): OK
Push Status: OK
Staging Application 'gaurishblog': OK
Starting Application 'gaurishblog': OK{% endhighlight %}

If you see output similar to above, you have successfully created an application. if it fails to try checking the logs

{% highlight sh %}af logs gaurishblog --all{% endhighlight %}

	
  6. **Migrate database:**appfog doesn't offer with direct access to database. so I created a tunnel to reach mysql using caldecott gem & import SQL dump file into mysql. Please note the tunnelling support is not available in all locations(ex not available in Asia, Europe). {% highlight sh %}
$ gem install caldecott
$ af tunnel
1: mysql-gaurishblog
Which service to tunnel to?: 1
Binding Service [mysql-gaurishblog]: OK
Stopping Application 'caldecott': OK
Staging Application 'caldecott': OK
Starting Application 'caldecott': OK
Getting tunnel connection info: OK

Service connection info:
  username : uXopxxxxmeI7
  password : plwWxxxxxekQPg
  name     : db25966b4xxxxxxxxxxx7dc515acf2c4

Starting tunnel to mysql-gaurishblog on port 10000.
1: none
2: mysql
3: mysqldump
Which client would you like to start?: 1
Open another shell to run command-line clients or
use a UI tool to connect using the displayed information.
Press Ctrl-C to exit...
{% endhighlight %}

at this point the remote mysql database is been tunneled on your localhost.   you can use the given the Service connection info given above to import data using Mysql CLI client or install GUI client like [Mysql Workbench](http://www.mysql.com/downloads/workbench/).for mysql CLI client, open a new command prompt or terminal and enter

{% highlight sh %}
$ mysql --protocol=TCP -P 10000 -h localhost -u uXopxxxxmeI7 -p'plwWxxxxxekQPg' db25966b4xxxxxxxxxxx7dc515acf2c4 < /path/to/mysqldump.sql
{% endhighlight %}

For Mysql Workbench, use the following parameters: 
[![](http://i.imgur.com/KKzuq.png)](http://imgur.com/KKzuq)

	
  7. **Custom Domains**: Now, my site was running on `gaurishblog.aws.af.cm` but I need to map it gaurishsharma.com. Good thing is Appfog allows to set up custom domains even on free plan! to make it work, I had to do two things. first, add _gaurishsharma.com_ to Domain name list in web console. Second, create a new CNAME record for _www.gaurishsharma.com_ pointing to _cname01.us01.aws.af.cm_. This worked but I still need to resolve _gaurishsharma.com_. However, as noted in the Web Console -> Domains, currently root-level domains are not supported. so As a workaround, I setup a URL forwarder using [cloudflare's page rules](http://blog.cloudflare.com/introducing-pagerules-url-forwarding) to send all traffic from root domain(_gaurishsharma.com_) to _www.gaurishsharma.com_. Worked Perfectly
 
 ![cloudflare](http://i.imgur.com/tvZte.png)




### Initial Impressions
	
  * **No Vendor Lock-in, Multiple Clouds**: As said earlier, Appfog allows you to choose which between different cloud platform along with server locations which is cool, if you don't want to rely on single vendor & establish multi-cloud solution. And incase you are worried about lock-in with Appfog itself, you might be pleased to know that Appfog is based on VMware's opensource Cloudfoundry platform.

	
  * **Free Plan** which gives you generous resources which is compelling reason to try Appfog.Also, Appfog seems like excellent platform to run your personnel blog on for FREE

	
  * **Command Line tool is swiss army knife: **the af CLI tool is handy and works well. Af gem can manage everything related to your appfog account with ease.

	
  * **Web console is a dud:**, works sometimes but sometimes starts spliting out errors for some reason. Example, I tried creating a new php app at AWS Singapore from their web control panel & [nothing was created](http://i.imgur.com/wocw7.png). app didn't show up, tried multiple times; [didn't work](http://i.imgur.com/Z8Krw.png). sometimes the app would show up in the app list but open it in browser but then nginx would throws 404 - page not found error at you.  This left a bad first impression & bitter taste as Appfog is not beta service but they want to be used as platform to host production applications! But to credit of appfog, they reached out to me on [Hacker new](http://news.ycombinator.com/item?id=4305133) & offered support on [twitter](https://twitter.com/gaurish/status/229152276768518144)(even though I was free user!). In morning the same app which was throwing 404, started working just fine. I was greeted with Wordpress 3-step install screen.

	
  * There are **Rough edges:**  There are some of rough edges.When I uploaded my blog files to appfog using _af update. _the process worked flawlessly(no errors) & blog did start to appear. But few minutes after, mischievously nginx gave 404s. Later, I checked logs & found that I was exceeding disk-space limit of 100mb.      My fault but the thing is at no-point I was informed that I had exceeded diskspace nor there were any errors  during af update or af push.  This should have been handled better.

	
  * PHP Platform: As per [phpinfo()](http://php-info.aws.af.cm/)They seems to be using standard packages provided Ubuntu with which support all common php extensions. further, the storage is not writable which the same with all mordern PaaS. Nothing wrong but something you have to keep in mind specially for PHP apps like Wordpress.




### Conclusion


Inspite of all its current bugs, AppFog is a seems a promising PaaS platform because it is cheaper than other PaaS specially if you are running CPU intensive applications, their pricing model is simple, supports multiple runtimes,clouds & service locations. And not to mention they seem to have good support. I personally, would use Appfog to host my blog & host my rails application under development.

What about you? How is your experience with Appfog
