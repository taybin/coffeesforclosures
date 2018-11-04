---
title: MacOS X memory alignment
date: 2007-04-03T21:23:46+00:00
author: Taybin Rutkin
---

I had a hard time finding a definitive statement on MacOS X memory alignment so I did my own tests. On 10.4/intel, both stack and heap memory is 16 byte aligned. So people porting software can stop looking for memalign() and posix_memalign(). It&#8217;s not needed.
