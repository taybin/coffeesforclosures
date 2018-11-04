---
title: What the hell, autoconf?
date: 2008-12-26T23:00:50+00:00
author: Taybin Rutkin
---

There&#8217;s a new autoconf out, autoconf-2.63.  It continues autoconf&#8217;s fine tradition of having the suckiest release schedule and quality of the GNU toolkit.  You would think that they would increment the major number whenever they release a non-backwards compatible release, but they don&#8217;t for shear perversity.  I guess 2.63 just rolls off the tongue, and I can&#8217;t blame them.  The ridiculousness of having to test for different versions of your platform configuration tool boggles me.  I&#8217;m at a loss for words at how much the autoconf maintainers have failed their core mission.

I&#8217;m not even going to go into their choice of m4 as the file format.  That probably made sense at the time. But that the thing is implemented in sh is just stupid.

Really, what the autoconf maintainers should do is what the make maintainers never had the guts to do.  Realize that their software is making the world a worse place, pick a worthy successor, and never update their project again.  In my perfect world, autoconf is allowed to commit hari-kari.  Meanwhile, automake is lined up against a wall and shot at dawn.

On the plus side, this might be the chance for everyone to finally move to a sane build tool like [waf](http://code.google.com/p/waf/) or [cmake](http://www.cmake.org/).
