---
layout: post
title: Installing Ruby from Source on Ubuntu 12.04 LTS
---

If you need to install ruby on server, I would suggest Compiling it from source because
  - When Source gets compilied on machine, you can apply compiler optimizations & get best possible performance
  - Its a global install & available system side
  - Its easiest way to install ruby.

## Here is what We will do:
Compile & Install Ruby `v2.1.1`

## Here is what you will need:

 - Server running Ubuntu 12.04 with root access to it.
 - basic command line know-how
 - 15mins of your time


## Step 1: Install required Dependancies

```sh
$ sudo apt-get -y install build-essential libssl-dev libffi-dev libyaml-dev \
git libtool libxslt-dev libxml2-dev libpq-dev gawk curl pngcrush imagemagick \
python-software-properties libreadline libreadline-dev

# If you're on Ubuntu >= 12.10, change:
# python-software-properties to software-properties-common
```

## Step 2: Install Ruby from Source

Download source tarball

```sh
$ wget http://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.1.tar.gz
```
Extract & CD into it

```sh
$ tar xf ruby-2.1.1.tar.gz
$ cd ruby-2.1.1/
```

Now, last step do infamous configure, make & make install

```sh
$ ./configure --disable-install-doc
$ make && make install
```
If everything went well, you should have latest ruby installed

```sh
$ ruby -v
ruby 2.1.1p76 (2014-02-24 revision 45161) [x86_64-linux]
```

Note: Incase of upgrade to newer version, just do the step 2 again. changing `2.1.1` with the latest version no.
