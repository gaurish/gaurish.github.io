---
layout: post
title: Getting Rails Test Suite Running on JRuby
---
This post is about Issue #11700 - Getting Rails Test Suite to run on Rails. Incase you don't have time to read the full post, see the following presentation.

<script async class="speakerdeck-embed" data-id="eebd7710970e013157f47aa36fe2d40f" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>


## Prologue
You are a ruby developer & want to run rails on anything other than CRuby/MRI which is the de-facto ruby implementation written in C. Reasons could the that you are having problems with GC, need fully multi-threaded env(no GVL/GIL) or you just curious like me. so, you research a bit & find that there is this thing called JRuby which is implemntation of ruby programming language that runs of battle-tested & rock solid [JVM](http://en.wikipedia.org/wiki/Java_virtual_machine). JVM is the same VM which is used by Java & all other JVM based languages like scala, closure, JPython etc.

### Installing JRuby
Installing JRuby seems seems quite simpler compared MRI/CRuby as its only dependancy of JRuby is the JVM. so, download [JDK 7 from oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) & [download/install JRuby from jruby.org](http://jruby.org/download)

### You liked JRuby
lets assume you tried JRuby on Devloplement machine & liked JRuby because:

1. You need for specific Java libraries & JRuby Allows you to call any Java library from ruby.
2. want to real Concurrency, not GVL/GIL contrainted provided by CRuby/MRI.
3. Better GC which helps with long running processes
4. Better Performance

So next question you ask is:

## Does Rails support JRuby?
Yes. Rails runs on JRuby out of the box but its on different Level of support that rails test suite fails to run, it fails. Current status is *allowed failures*

> *We consider any bugs on JRuby to be real bugs that need fixed, we just don't actively run the test suite against JRuby*
>                         -- **Steve Kalbnik** (Rails Core Committor) on [#11700](https://github.com/rails/rails/issues/11700#issuecomment-21955029)

But as rails is open-source, which means you can help to get test suite running. Pull Request are welcome.

## How to Run Rails Test Suite on JRuby
### Grab Rails Code:
```sh
$ git clone http://github.com/rails/rails.git
```
### Switch to JRuby
```sh
$ rvm use jruby #if using rvm
$ ruby -v
ruby 1.7.12 (1.9.3p392) 2014-04-15 643e292 on Java HotSpot(TM) 64-Bit Server
 VM 1.7.0_51-b13 [darwin-x86_64]
```
### Bundle Dependencies
```sh
$ cd /path/to/rails/checkout
$ bundle install
```
### Run Tests on particular component.
To run tests only for particular component(ActionPack, ActiveRecord, etc.).  All you need to do is to cd into that component directory & run `rake test`. For example, run `ActiveSupport` tests you can:


```sh
$ cd activesupport
$ rake test
```
### Run a particular test

```sh
$ cd activesupport
$ ruby -vIlib:test --client test/multibyte_chars_test.rb
ruby 1.7.12 (1.9.3p392) 2014-04-15 643e292 on Java HotSpot(TM) 64-Bit Server
 VM 1.7.0_51-b13 [darwin-x86_64]
/Users/gaurish/.rvm/gems/jruby-1.7.12@rails-dev/gems/minitest-5.3.3/
lib/minitest.rb:46 warning: (...) interpreted as grouped expression
Run options: --seed 21522

# Running:

lib/rational.rb is deprecated
.........................................................................
..............F....

Finished in 1.735000s, 53.0259 runs/s, 195.3890 assertions/s.

  1) Failure:
MultibyteCharsExtrasTest#test_tidy_bytes_should_tidy_bytes
[test/multibyte_chars_test.rb:657]:
--- expected
+++ actual
@@ -1 +1 @@
-"a€a"
+#<ActiveSupport::Multibyte::Chars:0xXXXXXX @wrapped_string="€a">


92 runs, 339 assertions, 1 failures, 0 errors, 0 skips
```

Okay, so now you have found a failing test. now, get this to <span style="color:green">green</span> & submit a Pull Request. And please don't forget to mention issue **#11700** in your PR, so everyone can track it that you are working on the changes.

For more info, please see:

- [Contributing to Rails Guide](http://edgeguides.rubyonrails.org/contributing_to_ruby_on_rails.html)
- [Issue #11700 - Getting Test Suite to run JRuby](https://github.com/rails/rails/issues/11700)
- [Send any Questions to rails core](https://groups.google.com/forum/#!forum/rubyonrails-core)
- [Report Rails Bugs](https://github.com/rails/rails/issues/new)
- [Report JRuby Bugs](https://github.com/jruby/jruby/issues/new)
