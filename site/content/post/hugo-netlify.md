+++
date = "2017-01-16T06:25:52-08:00"
description = "Hugo static website hosted on Netlify"
draft = true
tags = [
  "web",
  "howto"
]
title = "hugo netlify"
topics = [
  "blog",
]

+++

It took me a while to get this blog running properly and I think I should
record what I had to do in case I need to refresh my memory sometime. I've had
[plenty](http://t2o.blogspot.com) [of](http://poorpoorthing.posterous.com)
[before](http://upperrh.wordpress.com) including one which started out
as a
[statically generated one](http://frabjoustimes.magahiz.com) (in a Python script
I hacked together). Things have changed now and I wanted to do something that
didn't have so many tiers to it, just a simple virtually unhackable set of
static HTML pages that can be hosted somewhere with a content distribution
network.

There are [lots and lots of generators](https://staticsitegenerators.net/) out
there that will take your
[Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
files and compile nicely styled static files from partials so that you don't
need to do any of this on the server side. Among these, [Hugo](http://gohugo.io/)
appealed because of its efficiency and speed. I spent a lot of time at the end
of last year trying out [themes](http://themes.gohugo.io/), not all of which
are geared toward a personal blog. I knew I wasn't going to be designing my own
theme at this point because by now I know that layout isn't one of my talents.
In the end I went with the [Blackburn](https://github.com/yoshiharuyamashita/blackburn)
theme which looked nice and clean as it delivered just what I wanted.

My initial attempt to get this running on my desktop went pretty easily, but
the part I thought would be equally easy, hosting it on
[Github Pages](https://pages.github.com/)
