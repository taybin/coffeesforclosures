---
title: fftw and intel iMacs
date: 2006-05-31T21:03:52+00:00
author: Taybin Rutkin
---

If you are trying to compile [fftw3](http://fftw.org) on an intel iMac (or any Intel Core processor probably), you&#8217;ll need to pass to configure:

`<br /> --with-gcc-arch=prescott<br />`

That will prevent compiler errors complaining about illegal i386 instructions.
