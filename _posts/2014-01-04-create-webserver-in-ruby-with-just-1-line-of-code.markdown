---
layout: default
title: "Create WebServer in Ruby with just 1 line of code"
---

If you ever need a WebServer for quickly sharing of files or hosting static content, here is a ruby one-liner:


```sh
$ ruby -run -e httpd . -p 3000
```

This would spinup a simple webserver good for development & quick file sharing on Port 3000. works on `ruby v2` & above