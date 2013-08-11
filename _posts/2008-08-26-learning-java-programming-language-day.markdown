---
author: gaurish
comments: true
date: 2008-08-26 10:41:00+00:00
layout: post
slug: learning-java-programming-language-day
title: Learning Java Programming Language - Day 1
wordpress_id: 40
categories:
- Guides and Howtos
- Java
---

[![](http://4.bp.blogspot.com/_wMAC6frBFdw/SLPd0Yz1G_I/AAAAAAAAAP8/1SmO7sF290E/s200-R/java-logo_svg-a.jpg)](http://4.bp.blogspot.com/_wMAC6frBFdw/SLPd0Yz1G_I/AAAAAAAAAP8/s44Q_p7Dgx4/s1600-h/java-logo_svg-a.jpg)


I am Learning Java programming language these as its part of my course. Java is [Object-oriented](http://en.wikipedia.org/wiki/Object-oriented_programming), [structured](http://en.wikipedia.org/wiki/Structured_programming), [imperative](http://en.wikipedia.org/wiki/Imperative_programming) language. Its syntax(grammar) is heavily inspired  from  _C/C++_. All those coders who have know basics of C/C++ won't have much problems in learning java. Sun Microsystems defines java as
_The Java programming language is a high-level language that can be characterized by all of the following buzzwords: _Simple,Architecture neutral,Object oriented,Portable,Distributed,High performance,Multithreaded,Robust,Dynamic,Secure

The main Advantage of _Java_ is Portability, the code written in java can run on different platforms; independent of OS its coded. It can run on various platforms since its does not directly access the Host OS's libraries and API's . All code written in java is first compiled to bytecode by _java compiler_(javac) and the _java_ launcher tool runs your application instance in [Java Virtual Machine](http://en.wikipedia.org/wiki/Java_virtual_machine)(JVM).This method of running program allows programs to be platform independent as your code never comes in direct contact with host OS's programming API. a mediator called _Java Virtual Machine_(JVM) with help of _Java Application Programming Interface_ (API) automatically converts bytecode into machine readable code. The main disadvantage of [Virtualization](http://en.wikipedia.org/wiki/Virtualization) technique is that it sacrifices on performance for portability. Java Applications are resource intensive and are slower than native applications.
For example [Vuze](http://www.vuze.com/)(Formerly known as Azureus) is  bittorrent Client entirely coded in java. it needs minimum of 256mb Memory and lots of CPU time. it runs on Windows,Mac OS,Linux etc. However its counterpart _µTorrent _runs exclusively on Windows platform and takes marginal resources. As a Developer when choosing which programming language to code your application in  you have to decide between speed & portability.Java is highly portable so it should be used in making web applets and writing big applications in java should be generally avoided.

**Writing First Program in Java**
Before we can proceed writing famous "Hello World" program, we need to setup environment accordingly. for coding in any High-level programming language we nee three basic things compiler,Text editor and Shell. for java we would need



	
  * Language Compiler - _Java Development kit(JDK)_

	
  * Text Editor - Notepad++

	
  * Shell/Console - depends on Platform, we would use _Windows Command Shell _aka _cmd_


Download JDK from **[here](http://java.sun.com/javase/downloads/index.jsp)****(**74mb). Notepad++ from [**here**](http://www.filehippo.com/download_notepad/)(2mb). please note confuse notepad++ with windows notepad, both are entirely different. you can write your programs in notepad as well but windows notepad does not support basic programming functions like syntax highlighting. So its wise to use Notepad++.
Installing JDK and notepad++ is real easy, its typical Next,Next,Next Wizard. after you finish installing Next Step is to open Notepad++ and type the following code.

    

{% highlight java %}
    public class hello
    {
        public static void main (String args[])
        {
            System.out.println("Hello World. My First Java Program!");
        }
    }
{% endhighlight %}
Now save the file with .java extension and click on "**Show console Dialog**" icon from Standard toolbar in Notepad++. type "_cmd" _and you will get Windows Command Shell.
Compling the program
{% highlight sh %}
  javac filename.java
{% endhighlight %}
Running the Program
{% highlight sh %}
  java filename
{% endhighlight %}
make sure you are in dir where the file exists.
**ScreenShot:**

[![](http://1.bp.blogspot.com/_wMAC6frBFdw/SLPZj1e4msI/AAAAAAAAAPs/rJNmFLyH7K0/s320-R/notepad_java.JPG)](http://1.bp.blogspot.com/_wMAC6frBFdw/SLPZj1e4msI/AAAAAAAAAPs/66GOgnqb2hQ/s1600-h/notepad_java.JPG)


 [![](http://2.bp.blogspot.com/_wMAC6frBFdw/SLPZkNO0iAI/AAAAAAAAAP0/NQe-zreIgYY/s320-R/notepad_java2.JPG)](http://2.bp.blogspot.com/_wMAC6frBFdw/SLPZkNO0iAI/AAAAAAAAAP0/zkKUWKu02-Q/s1600-h/notepad_java2.JPG) 




you can also use a _Integrated Development Environment_(IDE ) like [Eclipse ](http://www.eclipse.org/)which has a Text editor,Complier and Shell integrated into one application. its bit more complex and is more usefull in coding large applications. 




For online resources on Java have a look [here](http://java.sun.com/docs/books/tutorial/), [here](http://www.freewarejava.com/tutorials/index.shtml) & [here](http://www.javaomatic.com/%20). For java Books try [Java™ Programming Language](http://www.informit.com/title/0321349806?aid=9f15cdfa-4e22-40dc-bfc9-cdc6322be0fd) by Arnold, Ken/Gosling, James/Holmes, David and  [Effective Java](http://www.amazon.com/Effective-Java-2nd-Joshua-Bloch/dp/0321356683) by Joshua Bloch




**
**




Wish you make fastest applications with little bugs**
**




**Happy Programming!
**
