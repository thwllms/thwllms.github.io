---
layout:     post
title:      "What's the toll on I-66? (dot com)"
date:       2019-06-24 09:00:00
summary:    VDOT's website wasn't cutting it, so I built my own.
categories: blog
---

TL;DR: I made a website - [whatsthetolloni66.com](http://whatsthetolloni66.com)

![:q]({{ site.images }}/whats-the-toll.gif)

Anyone who commutes to DC from Northern Virginia knows about the rush-hour
congestion pricing on I-66. HOV-2+ vehicles are free, but solo drivers can
expect to pay [a
_lot_](http://www.fox5dc.com/news/local-news/i-66-express-lanes-toll-spikes-to-46-for-tuesday-morning-commute).

Occasionally I have to drive toward DC for work. I-66 is usually the fastest
route, but toll prices can be all over the place ($20 from I-495 to DC is not
unusual, although with light traffic it can be less than $5). I've tried
checking VDOT's [vai66tolls.com](vai66tolls.com) website before heading out, but
the price always changes by the time I actually get to I-66. Quickly checking
the site on my phone is _not_ an option - the interface definitely isn't
intended to be used on mobile devices.

A while ago I decided to scrape the I-66 toll data from VDOT's website. This
turned out to be more difficult than I assumed.  The VDOT site's interface sends
multiple POST requests back to the server before the toll is actually returned.
It took a while to figure out what these requests actually accomplish,
especially since the requests include lots of extraneous form data. Eventually I
arrived at Python script that could replicate the series of requests and extract
the toll for a given route.

Recently I transformed that Python script into a small API with Flask and got it
running on AWS Lambda. Then I built a really basic React UI - which is
definitely overkill, but whatever. So... here it is:
[whatsthetolloni66.com](http://whatsthetolloni66.com)

Not much, but actually pretty useful. Planning to add new features here and
there.
