---
author: gaurish
comments: true
date: 2012-05-19 15:37:56+00:00
layout: post
slug: ruby-vs-java-why-do-i-like-ruby-more
title: 'Ruby vs Java: Why do I like ruby more'
wordpress_id: 688
categories:
- Ruby
---

I dislike java, by dislike I mean I do not enjoy programming in java but I still use it in situations where java feels best tool for the job, because I am technology agnostic & belive in using best tool for the job; for example writing Android Apps. And I admit I enjoy writing ruby code that much more than java that I will even write ruby from my deathbed. sounds crazy! I know!. But it's not fanboyism, because for writing webapps -- ruby & the rails stack is TEH best. In future, if something better comes along, I would switch in a heartbeat because I really believe in using best possible tools to get the job done

Now, let's go back to the reason of this blog post. Why do I like ruby more:
well, there are [lot](http://myloveruby.herokuapp.com/) of reasons but for me, the main reason is the philosophy behind the langauge


> 

> 
> ### Ruby is designed to make programmers happy
> 
> 
- _Matz, Creator of Ruby_


To explain this, consider this ruby code:

[ruby]
5.times {print "My Name is Gaurish "}
[/ruby]

so even if you do not know ruby programming or heck do not know programming at all, I am pretty sure you can know what this code is doing does just by reading aloud words by word. Why, because it reads like "_5 times print my name is_ gaurish".

Lets take another example, this time a bit more complex , to read a file & then print it.  here is the code to do that in Java

[java]
class FileOperations{
static void readfile(String filename) throws FileNotFoundException {
  File input = new File(filename);
  String line;
  Scanner reader = null;
  try {
    reader = new Scanner(input);
    while(reader.hasNextLine()) {
      System.out.println(reader.nextLine());
    }
  } finally { reader.close(); }
}
public static void main(String args[]){
 readfile("hello.txt");
}[/java]

}

now, compare this to ruby code which does the same thing without using classes which is mandatory in java.  Another thing is, the Java version needs to wrap the creation of the Scanner in a `try` block so it can be guaranteed to be closed.Now, lets compare this to ruby version of same program

[ruby]
def readfile(filename)
  File.open(filename, "r") do |f|
    f.each_line {|line| print line }
  end
end
readfile "hello.txt"
[/ruby]

Because of the existence of blocks, it is possible to abstract away the need to close the File in a single location, minimizing programmer error and reducing duplication. And this is one of the reason, I like ruby more than Java. There are plenty of other reasons & maybe I will cover those in future posts, if anyone is interested, then leave a comment below

PS: I have used print, instead of puts because to highlight the readability of ruby. But if you write ruby more, you will find yourself using puts as it auto inserts a new line which has to be manually inserted when using print.
