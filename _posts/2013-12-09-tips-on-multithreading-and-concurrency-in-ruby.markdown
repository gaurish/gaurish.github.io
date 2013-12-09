---
author: Gaurish Sharma
layout: post
title: Tips on MultiThreading & Concurrency in Ruby
Categories:
- Programming
- Ruby
---
If you are a rubyist, chances are that you might have faced some problem which was slower/not possible using traditional single thread approach. so here are are few tips what might help you when working with thread in Ruby.

1. Threading is hard. Don't use thread, until you really need them. Threading opens can of worms. 
2. If you do opt to use Threading, don't share/change data between multiple threads. You will get crazy data which will be different on every run.
3. If you want to share/change data in critical section, use  semaphore/mutex, so you can lock parts of code should change as part of a "transaction", so other threads waiting to change the data would be blocked.
4. set `Thread.abort_on_exception = true`. By Default, ruby will continue even if there is a error in a child thread. Never giving you chance to view the exception raised. Setting `Thread.abort_on_exception = true` will abort ALL threads if an exception is raised, giving you a chance to debug. `Thread.abort_on_exception` is a global flag so set in your config or on top of the file BEFORE any threading code. 
5. Never use `Thread#Join` without a timeout. Join does not return untill ALL running threads exit. Which means if you have a thread which is waiting on something, join will also keep waiting endlessly. solution: Use a sensible timeout value. example `t.join(5)` where 5 is seconds.
6. Ruby's Core Data Structures are NOT tread-safe. It is another way of saying -- data structures like Array, Hash are not fit to use when writing treaded code. fortunately, there are third-party libs which are atomic & work exactly like Hash, Array ruby. notable one is [thread_safe gem](https://github.com/headius/thread_safe) is also used by rails. 
