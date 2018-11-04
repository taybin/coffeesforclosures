---
title: The Power of Binary Searching
date: 2007-08-21T21:44:45+00:00
author: Taybin Rutkin
---

I always knew that [binary searching](http://en.wikipedia.org/wiki/Binary_search) was fast, O(log<sub>2</sub>) and all that. But when you have to run it by hand over 3000 subversion revisions, looking for the place where you introduced a memory leak, and after four steps you&#8217;ve eliminated 93% of the search space, you get a new appreciation for it.

There are some tools out there for automating these searches through subversion. They didn&#8217;t fit our problem though because determining whether we were showing a memory leak was fuzzy.

Turned out to be 4 memory leaks. Two very minor ones, and two major ones in third party libraries, one of which only showed up on the Mac platform.

Thanks to binary searching, we could quickly identify the exact spots where these leaks were introduced.
