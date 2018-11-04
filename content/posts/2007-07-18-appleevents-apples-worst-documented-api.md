---
title: "AppleEvents: Apple&#8217;s worst documented API?"
date: 2007-07-18T21:37:40+00:00
author: Taybin Rutkin
---

If you are trying to register a callback on getting a URL passed to your program through AppleEvents, don&#8217;t use the documented kAEInternetSuite and kAEISGetURL enums. They are defined as &#8216;gurl&#8217;, but the actual value passed to your program is &#8216;GURL&#8217;. From what I can tell, everyone defines their own enums because this is well known.

Apple can&#8217;t fix it though, because it would break everyone&#8217;s software. So they keep documenting it as &#8216;gurl&#8217;, and we keep redefining it to the actual value.

Awesome.
