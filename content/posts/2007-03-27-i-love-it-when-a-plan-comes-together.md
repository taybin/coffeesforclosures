---
title: I love it when a plan comes together
date: 2007-03-27T21:22:46+00:00
author: Taybin Rutkin
---

With some help from [Daniel Jalkut](http://www.red-sweater.com/blog/23/automatic-build-sub-versioning-in-xcode), [Dave Dribin](http://www.dribin.org/dave/blog/archives/2006/08/02/versioning_os_x_apps/), [Chris Hanson](http://chanson.livejournal.com/125568.html), and of course [Andy Matuschak&#8217;s Sparkle](http://sparkle.andymatuschak.org/) and [Reinvented Software&#8217;s Feeder](http://reinventedsoftware.com/feeder/), I finally have a system for pushing Gusto updates that are tied to SVN revision numbers. Once it works, it works pretty good. I might run into some trouble in the future if I were to use a different tree than trunk, but that&#8217;ll be a good ways away.

I&#8217;m not too worried either because:

a) agvtool will let me set whatever version and marketingversion I want

b) Sparkle will let me explicitly name the next version
