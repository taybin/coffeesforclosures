---
title: Objective-C and libsigc++
date: 2006-08-31T21:16:42+00:00
author: Taybin Rutkin
---

I&#8217;ve started working on a secret MacOSX project. I decided to use Apple&#8217;s Cocoa framework, so that means I have to use Objective-C. The backend I&#8217;m basing my project on is in C++ and uses the libsigc++ callback library as an important component of its interface with the frontend. So how do you setup ObjC methods to be called back?

Use my [glue header](http://www.taybin.com/wp-content/uploads/2006/09/objcsigcglue.h). It will create glue functions at compile time for calling objc_msgSend() with the appropriate arguments.

Example:

<pre>SignalActivated.connect (sigc::bind(sigc::ptr_fun(objcsigcglue&lt;bool>), self, @selector(CatchSignal:)));
</pre>

This will call [self CatchSignal:boolValue]. Pretty neat, right? For the majority of callbacks that don&#8217;t accept arguments, a mere function pointer cast is needed:

<pre>BoringSignal.connect (sigc::bind(sigc::ptr_fun((msgFtn)objc_msgSend), self, @selector(boringSignalCatch:)));
</pre>

_Update: I fixed [objcsigcglue.h](http://www.taybin.com/wp-content/uploads/2006/09/objcsigcglue.h) to work with references that are passed to the callback. It should be much more flexible with other types I haven&#8217;t anticipated too._
