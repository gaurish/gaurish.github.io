---
author: gaurish
comments: true
date: 2012-12-16 15:41:34+00:00
layout: post
slug: contributing-to-ruby-on-rails-a-guide
title: Contributing to Ruby on Rails - A Guide
wordpress_id: 785
categories:
- Programming
- Ruby
---

Recently, I have started contributing to [Ruby on Rails](http://rubyonrails.org/) -- the popular web framework for quickly building web applications. I have just started but [couple of my commits have been merged into rails core](http://contributors.rubyonrails.org/contributors/gaurish-sharma/commits) &  have a pretty good idea on contributing to rails. this guide details how you can start contributing to rails.


## Step 0 - Decide what to contribute


It could be a bug or feature that you want aka starch your itch. It could a bug fix in which cause check github issue tracker for existing issues & see if you can fix anyone of them and send a Pull Request. It could be removing a warning from test. Or it would contributing documentation.


## Step 1 - Fork & Change


This is rather simple but you must know how to use git - the popular distributed version control system. If you don't then please following this guide closely & read multiple times until you understand.



	
  * Goto rails page on github & click the "Fork" button on the top. requires github account. so register if not already done. Its free!

	
  * You've successfully forked rails, but so far it only exists on GitHub. To be able to work on the project, you will need to clone it to your local machine.
{% highlight sh %}
git clone https://github.com/your_github_username_goes_here/rails.git
# Clones your fork of the repo into the current directory in terminal
{% endhighlight %}

	
  * Create a new branch{% highlight sh %}
$ git checkout -b my_branch
{% endhighlight %}

	
  * Create new rails app based on your fork
{% highlight sh %}
$ /replace/with/path/to/your/rails/fork/railties/bin/rails new app_name_goes_here --dev
        {% endhighlight %}

	
  * Do your changes. Now whatever changes you do, would instantly get reflected into your rails app. Once you are okay with said changed, commit them
{% highlight sh %}
$ git commit -a -m "Describe your change in this message"
            # commit your changes. make sure to follow the guidance of a good commit message
       {% endhighlight %}




## Step 2 - Create a Pull Request


so you have made your change, tested it.Sweet! Now, its time to send your awesome changes to rails core team for review.



	
  * Add Upstream:
{% highlight sh %} $ git add remote git@github.com:rails/rails.git {% endhighlight %}

	
  * switch back to master, pull latest changes
{% highlight sh %}
$ git checkout master
$ git pull --rebase upstream master
{% endhighlight %}

	
  * Switch back your branch & Reapply your changes ontop of latest changes of the rails' upstream master
{% highlight sh %} $ git checkout my_branch
$ git rebase master
{% endhighlight %}


	
  * In the process of the rebase, it may discover conflicts. In that case it will stop and allow you to fix the conflicts. After fixing conflicts, use **git add .** to update the index with those contents, and then just run:
{% highlight sh %}
$ git rebase --continue
{% endhighlight %}

	
  * Push branch to GitHub
{% highlight sh %}
$ git push origin my_branch --force
{% endhighlight %}


	
  * Open Pull request using [github's web-interface](https://help.github.com/articles/using-pull-requests).


Congratulation on your contribution! Now, wait for comments on the Pull request.


## Step - 3


Once your Pull request is opened, most probably someone will suggest 1 or 2 changes. hers is how to do them:



	
  1. switch to your feature branch
{% highlight sh %}
$ git checkout my_branch
{% endhighlight %}


	
  2. make changes & commit

	
  3. squash changes into one commit. rule is one feature == one commit

	
  4. force push


To close, let me welcome you the world of open source. where code you write gets used by thousands of developers & affects lives of millions of people around the world. Its pretty amazing!
