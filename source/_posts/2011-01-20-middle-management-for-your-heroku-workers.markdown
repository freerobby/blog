---
comments: true
date: '2011-01-20 10:52:03'
layout: post
title: Middle Management for Your Heroku Workers
categories: [Technology]
---

Heroku provides a highly scalable [background worker framework via delayed_job](http://docs.heroku.com/background-jobs), but leaves the burden of scaling it to the user. Several people have tried to solve this by either [forking the delayed_job gem](https://github.com/wxmn/delayed_job) or hooking into the gold standard [collectiveidea gem](https://github.com/phaza/Heroku-Delayed-Job-Autoscale). I like the latter approach, but haven't seen an implementation that meets my requirements.<!--more-->

Specifically, I want the following in my scaling library:

1. Don't require any special third party forks.

1. Let me set minimum and maximum worker counts -- and change them without redeploying.

1. Let me set how busy I want my workers to be.

1. Work out of the box with minimal configuration.

To achieve these things, I built [middle_management](https://github.com/freerobby/middle_management).

You can get up and running with it very quickly:

1. Add "middle_management" to your Gemfile

1. Set the required heroku environment variables (MIDDLE_MANAGEMENT_HEROKU_USERNAME, MIDDLE_MANAGEMENT_HEROKU_PASSWORD, MIDDLE_MANAGEMENT_HEROKU_APP, MIDDLE_MANAGEMENT_MIN_WORKERS, MIDDLE_MANAGEMENT_MAX_WORKERS).

1. Deploy.

The [code](https://github.com/freerobby/middle_management) is on github and the [gem](https://rubygems.org/gems/middle_management) is on Rubygems. Check out the [readme](https://github.com/freerobby/middle_management/blob/master/README) for further details.
