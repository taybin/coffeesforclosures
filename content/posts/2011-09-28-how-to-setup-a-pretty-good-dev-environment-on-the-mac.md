---
title: How to setup a pretty good dev environment on the mac
date: 2011-09-28T22:04:05+00:00
author: Taybin Rutkin
---

(This was a quick write up for a coworker, but others might find it useful)

This assumes you have XCode. I mean, really now.

First thing to do is install [mac homebrew](http://mxcl.github.com/homebrew/). It&#8217;s a package manager of useful open source software. You install it by pasting into the terminal:

<pre>/usr/bin/ruby -e "$(curl -fsSL https://raw.github.com/gist/323731)"
</pre>

then just to make sure it&#8217;s working, run:

<pre>brew install -v git
</pre>

Next we want to install the [node package manager](http://npmjs.org/).

It&#8217;s a simple

<pre>curl http://npmjs.org/install.sh | sh
</pre>

Lastly, I like to setup [rvm](http://beginrescueend.com/), for managing multiple ruby installations and keeping my base machine clean of stray gems.

<pre>bash &lt; &lt;(curl -s https://rvm.beginrescueend.com/install/rvm)
</pre>

RVM is a little more complicated since you also have to add a little something to your shell file so that the paths are loaded correctly

<pre>echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm"
</pre>

That's \*about\* it. I'm still looking into how to setup the RVM equivalent for python, but it seems that community is still figuring out their tools and a clear solution hasn't emerged yet.
