---
author: gaurish
comments: true
date: 2012-04-14 12:39:10+00:00
layout: post
slug: enable-gzip-compression-for-rails-3-2-on-heroku-cedar
title: Enable gzip compression for Rails 3.2 on heroku Cedar
wordpress_id: 679
categories:
- Programming
- Ruby
---

Heroku is the popular ruby on rails PAAS hosting platform. With the earlier versions, if you were hosting a rails web application on it. All apps deployed to Heroku used to automatically compress pages they serve, by passing through Nginx’s gzip filter on the way out. But with their newest [Cedar Stack](https://devcenter.heroku.com/articles/cedar), things have changed

In Cedar, the HTTP requests terminates directly at your app server & no longer goes through a proxy server(Nginx), hence there can't be automatic gzip compression. More information about this can be found in [HTTP routing dev center article](https://devcenter.heroku.com/articles/http-routing) So we have to manage gzip compression on our own. fortunately, this is trivial as adding just one line to your config. basically, you will need to use **Rack::Deflater **& make sure that it get loaded before ActionDispatch::Static. The simplest way to enable gzip compression in Rails 3.2 is by adding "use **Rack::Deflater**" in _config.ru_ file.

After the change, this how your config.ru file should look like:

[ruby]
# This file is used by Rack-based servers to start the application.

require ::File.expand_path('../config/environment',  __FILE__)
use Rack::Deflater
run Improvingoutcomes::Application
[/ruby]

I spending sometime gather information about this. So Hope this post help you save some time.
