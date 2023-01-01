+++
date = "2017-02-04T11:10:52-08:00"
description = "What I did to be able to log in to Twitter again"
draft = false
tags = [
  "browser",
  "howto",
  "chrome"
]
title = "Google Chrome Twitter MFA Login Fail"
topics = [
  "blog",
  "computer"
]

+++

Posting this here in case it saves someone else some time troubleshooting.

I was having lots of problems with Tweetdeck on Windows 10 in Chrome over the
last couple of weeks. I hadn't enabled any new plugins or anything like that,
but I was wondering whether the cookies were messing things up, so I logged
out, cleared content, and tried logging back in. Surprise, it said my username
and password were not recognized. I tried entering this a few times before I
remembered that I'd enabled multi-factor authentication security on Twitter
a few weeks back, and for some reason it wasn't prompting me to input the
numeric code that was supposed to be texted to my phone. My other devices were
working okay. Same thing happened when instead of logging in to Tweetdeck I just
tried the main twitter.com site. I started wondering whether the popup alert
about MFA was being blocked for some reason in Chrome.

I tried logging in to Twitter through Microsoft Edge (a browser I almost never
use) -- it prompted me for the token the way it was supposed to and I was in.
Then I went back to Chrome, opened an incognito window, and was able to log in
there without a problem.

That's when I realized that my password field in Chrome was being pre-filled. I
must have told it to save that password at some time a long time back, even
though I have Lastpass to remember all my logins. So I cleared all my saved
passwords, got out of incognito mode, and tried loggin in to Twitter again.
Bingo, it prompted me for my second factor and I was in. Same thing worked for
Tweetdeck. So the solution to the trouble was to not have the browser remember
passwords when using MFA security.
