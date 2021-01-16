+++
date = "2017-01-16T16:13:52-08:00"
description = "Hugo static website hosted on Netlify"
draft = false
tags = [
  "web",
  "howto"
]
title = "Hosting a Hugo generated blog on Netlify"
topics = [
  "blog",
  "networking"
]

+++

<div align="center" style="font-size:x-small"><img src="/hugo.png" width=202 height=230 alt="Hugo logo" />
<img src="https://milkfish08.s3.amazonaws.com/photo/blog/netlify.svg" width=278 height=100 alt="Netlify logo" /></div>

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
[Github Pages](https://pages.github.com/), I never did get working properly. I
tried following the step-by-step tutorial on the Hugo site along with the
description of how to set things up at my domain registrar
[Namecheap](https://www.namecheap.com/) but everything I tried led either to
unresolvable URLs or infinite redirect loops. Part of the problem was that none
of the network setup was controlled by me directly, but was being carried out
on my behalf in ways I couldn't see. I think the tutorials were unfortunately
not being kept up to date with the current operation of Github Pages along with
much of the other pages of advice I could find on the Web.

I think it was when I was looking around the hundreds of
[Hugo issues area in Github](https://github.com/spf13/hugo/issues) I might have
first seen mention of free hosting at [Netlify](https://www.netlify.com/) as
being a less trouble-prone alternative to Github Pages. I set up an account
there and got it linked with my Github archive. They support a tool called
[Victor Hugo](https://github.com/netlify/victor-hugo) which allows them to
automate the site generation using node.js and Gulp. I didn't have too much
interest doing this on my workstations, but found that I could just adapt the
structure of my working directory to use it on their end (mainly just pushing my
content folder below a top-level folder named 'site', including the json and
js files they need to have in the root of the repository, and incorporating their
'src' directory) to get my site building on every git push. I didn't even have
to keep the complicated git subtree stuff that Git Pages wanted.

There were still some hiccups with DNS, but here fortunately Netlify had a
good tutorial on what to do on their
[blog](https://www.netlify.com/blog/2016/03/14/setting-up-your-custom-domain/#namecheap)
and I was finally able to view my site at the domain I'd purchased (for $0.88 US
annually). All that delay was not in vain because it gave me the time to generate
some content to start with anyway. Now all I have to do to create a new blog
post is to create a template with Hugo

```
hugo new post\hugo-netlify.md
```

(having compiled the Hugo source and placed the executable in my path) and then
use [Atom](https://atom.io/) to edit the Markdown. I can preview what I'm
writing by running Hugo as a local server

```
hugo server
```

which renders just about everything except for the parts which require running
on an actual host (such as disqus comments). I commit to the master branch
and push up to [the public repo](https://github.com/4thAce/zeroblog) and
the site rebuild takes only a minute or two on Netlify. I like having all my
posts tracked in Git and don't have to worry that a script kiddie will find
a zero-day vulnerability in my blogging engine to make their way into a
backend database, because there isn't one. The hosting takes care of all the
content distribution via [Cloudflare](https://www.cloudflare.com/)
so that the blog makes it out to everyone as quickly as  possible without my
having to manage anything.
