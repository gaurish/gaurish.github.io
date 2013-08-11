---
author: gaurish
comments: true
date: 2012-01-30 17:36:45+00:00
layout: post
slug: getting-started-with-drupal-module-development
title: 'Getting Started with Drupal Module Development '
wordpress_id: 658
categories:
- Web - Drupal
---

I am building a new site & I have chosen to create that with [Drupal](http://drupal.org/). as you may know, Drupal is a popular open-source, free to use Content Management System but you may not know that Drupal also has a powerful framework which can be used to be built just about anything. This is done by creating custom modules. Now, as with other things the hardest part is to get started. so this post will deal on how to get started with Drupal development


### Learning Drupal Module Development


In Drupal, Whatever you want to do. There is a modules for that! If not, then you have to write a custom module that accomplishes that.

**Introduction**

A Drupal module mainly consists of bunch of loosely coupled functions  written in procedural style(you can use some OO features though). some might ask why it's not object-oriented, that because Drupal was written in the time when PHP didn't support OOP & lacked namespaces. Sadly, that hasn't changed even when even now PHP does support full OOP including namespaces(PHP 5.3+).
However, it is commendable on Drupal's part that it managed to work around PHP's limitations by adopting design such architecture.

**Hook System**

Hook System is nothing but a glorified naming convention adopted universally by Drupal Community. Infact, entire architecture of Drupal is build around this naming convention. According to this naming convention, the module name you choose must be unique, and should be all lowercase, containing only letters & numbers, always starting with a letter. Within the module itself, all functions must then be prefixed with the module filename, followed by an underscore, and then action(called hook in drupal land) in following way

function ModuleName_action()

here,
ModuleName = name of your module
action = pre-defined hook

These hooks are pre-defined and are called automatically by Drupal when specific event occurs, so you just have to define an appropriate hook/action & Drupal will take care of the rest. for example, your module was called "mymodule" & want to add some help text. so, in custom module, you will add function named "_mymodule_help_".

[php]
/**
* This Implements hook_help()
*/
function mymodule_help($path, $arg){
    if($path=='admin/structure'){
        return t('This is the sample help text');
    }
}[/php]

This function gets called automatically by Drupal when a page is displayed, then we check if _$path_ is_ admin/structure,_ if yes. then the help text is displayed. Simple!

So, this was a 20,000 feet view to Drupal Modules. I hope now you have at least basic idea about Drupal's hook system, how it works,why its build that way & how go about writing custom modules. To end, I am leaving you with some resources that would guide you further on this journey of writing Drupal modules.



	
  * [Drupal API reference site](http://api.drupal.org/api/drupal)

	
  * **Books**: I am reading "[The Definitive Guide to Drupal 7](http://www.amazon.com/Definitive-Guide-Drupal-Apress/dp/1430231351)", however there are [lot of other options to chose from](http://drupal.org/books).

	
  * [Building Drupal Module - Drupal.org Docs](http://drupal.org/developing/modules)

	
  * [Examples Project](http://drupal.org/project/examples) - Standard repository of sample modules that can be used to learn module development,


Good Luck & have fun Drupalizing the web!
