---
title: AMD modules and web developers
date: 2011-10-19T22:07:11+00:00
author: Taybin Rutkin
---

Now that [require.js has reached 1.0](http://tagneto.blogspot.com/2011/10/requirejs-10-released.html), it&#8217;s probably time to start shouting its praises from every rooftop so that javascript library authors include support for it. Require.js is an implementation of the AMD draft specification which adds simple module support for javascript in the browser. This means no more namespace pollution (if you use it properly).

Unfortunately, we&#8217;re talking about web developers who don&#8217;t seem to understand basic principals like [avoiding namespace pollution](https://groups.google.com/forum/#!searchin/backbonejs/require/backbonejs/Z7Zb7UqhhOY/_PJcdmRyXNAJ). I mean, how can you even have a conversation with someone with such a misconception of good practices?

[Jeremy Ashkenas](https://github.com/jashkenas), the creator of CoffeeScript, Backbone, and Underscore also seems to have [misconceptions](https://github.com/documentcloud/underscore/pull/287) about the [purpose](https://github.com/documentcloud/backbone/issues/94) of AMD.

I was really hoping that someone with such a worthy track record would have seen the light by now. Luckily the require.js guy himself is pushing for [AMD support in Underscore](https://github.com/documentcloud/underscore/pull/338) with a new pull request. Once that is pulled in, it looks like [Backbone is next on the list](https://github.com/jrburke/backbone/commit/2715877df923defc17e1bdcf93da7767d54e6d6d).

Since the next version of [jQuery will have AMD support](http://bugs.jquery.com/ticket/7102), I imagine that the rest of the libraries will follow since they seem to look up to jQuery for best practices.

And then, one part of the [nightmare that is working with javascript](http://javascript.crockford.com/javascript.html) will be gone.
