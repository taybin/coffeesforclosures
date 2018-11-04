---
title: smart counting with dynamic_bitset and boost.framework
date: 2007-04-07T21:25:46+00:00
author: Taybin Rutkin
---

In [Ardour](http://ardour.org), we have numbered audio tracks named Track 1, Track 2, and so on. Most software when faced with what to name the next created track will just use a static int that is incremented with each track.

With Ardour, we wanted to make it smarter. We wanted to be able to re-add Track 1 if the first track was deleted. But not if the first track had just been renamed. We use C++ for the libardour backend, so we were in luck.

The [STL](http://www.sgi.com/tech/stl/) includes [bitset](http://www.sgi.com/tech/stl/bitset.html), a very handy wrapper for what&#8217;s essentially an array of booleans, but optimized for space.

The technique is: look for the first false slot in the bitset. The index is the number of the new track. When a track is deleted, mark the slot as false. This lets the user rename a track and it won&#8217;t interfere with the counting.

The one problem with this is the size of a bitset is set at compile time. You could use [vector<bool>](http://www.sgi.com/tech/stl/bit_vector.html), but its use is [discouraged](http://www.informit.com/guides/content.asp?g=cplusplus&seqNum=98&rl=1). Luckily, [boost.org](http://boost.org) has an implementation of [dynamic_bitset](http://boost.org/libs/dynamic_bitset/dynamic_bitset.html) which can be grown during runtime.

This smart counting gives Ardour a polish and the users love it.

I&#8217;ve created a [boost.framework](http://files.penguinsounds.org/frameworks/boost.framework.zip) for those of you lucky enough to be using C++ on OS X. It&#8217;s all header files, so you only need to include it in the frameworks path. It doesn&#8217;t need to be linked in. It unzips to a large size, but you only pay for what you use.
