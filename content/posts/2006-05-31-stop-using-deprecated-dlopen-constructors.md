---
title: Stop using deprecated dlopen() constructors
date: 2006-05-31T21:10:00+00:00
author: Taybin Rutkin
---

As I re-discovered for the third time last evening, [LADSPA](http://www.ladspa.org) programmers still haven&#8217;t made the switch from `_init()` to `__attribute__((constructor)) void init() {}`.

The older mechanism has been deprecated since the early/mid &#8217;90s. Most operating systems still supported it but with MacOSX 10.4, Apple dropped support when they [implemented](http://developer.apple.com/releasenotes/DeveloperTools/dyld.html) their own dlopen() support.

I&#8217;ve sent an [email](http://marc.theaimsgroup.com/?l=linux-audio-dev&m=113045466129402&w=2) about it to the LAD mailing list, but apparently no one listened.
