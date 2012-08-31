---
layout: post
title: "Migrating to Riak at Shareaholic"
date: 2012-08-31 10:30
comments: true
categories: [Technology]
---

Last night I presented "Migrating to Riak @Shareaholic" at the first [Boston Riak meetup](http://www.meetup.com/Boston-Riak/events/77828202)

Below are my slides from the talk.

<iframe src="http://www.slideshare.net/slideshow/embed_code/14130056?rel=0" width="597" height="486" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen> </iframe>

One correction that I've updated in the slides: I mistakenly referenced Shareaholic using Hadoop MapReduce. Shareaholic uses Amazon's Elastic MapReduce, which works similarly to Hadoop but is a separate implementation. My reference is intended only to distinguish it from Riak's MapReduce implementation, which is substantially different.
