---
layout: post
title: "AWS Risk Mitigation Strategies"
date: 2012-07-02 10:05
comments: true
categories: [Startups, Technology]
---

Even if you're not ready to roll your own hardware, there's a lot you can do to minimize your risk of downtime on AWS, and to mitigate the effects when it's unavoidable.<!-- more -->

### Plan for Brownouts Following Blackouts

Amazon [emphasizes](http://status.aws.amazon.com/) that only "a single availability zone" suffered EC2 and EBS outages, but that is only half the story. The cascading effects that followed are equally important.

For several hours on Friday night, I was unable to bring up a single instance in any of the five US-East availability zones. A commenter correctly [pointed out](http://news.ycombinator.com/item?id=4182137) that this is what light utilization reserved instances are for, but in this case that would not have helped. The AWS web console was unreachable, as was the AWS API. I was eventually able to get an "insufficient capacity" error message, at which point a reserved instance may have been helpful, but that was hours later.

I've confirmed that others had similar experiences. A source at a company with AWS Platinum Support told me that Amazon was throttling requests and the spawning of new instances in "unaffected" US-East availability zones. It sounds like a barrage of requests came in to launch new EC2 instances in these other availability zones, and Amazon was unable to support the demand.

At [Shareaholic](http://shareaholic.com) we determined a long time ago that implementing full redundancy was not worth the engineering cost. However, that was based on the assumption that if one availability zone went offline, we could bring up new instances in another one immediately to keep our core services operating. This proved to be a flawed assumption. We did not anticipate that the loss of one availability zone would create more demand than Amazon could handle in the other four.

### Use Automated Infrastructure to Save Time and Headaches

Without exception, what saves me the most time recovering from an AWS outage is that our infrastructure stack is automated with Chef. Deploying new code or provisioning a new server requires only one terminal command.

Automated infrastructure also provides an additional benefit: it serves as documentation for the configuration of every server. Not sure what your haproxy.cfg should look like? It's in Chef. Not sure how to setup your MySQL slave? It's in Chef.

Whether you use Chef, Puppet, Rubber or homegrown deploy scripts, having an automated infrastructure stack saves you time and ensures that you aren't struggling to piece together a working config file at a critical moment.

### Use Low TTL Values for Faster DNS Updates

At Shareaholic, we set a very low DNS TTL value (300 seconds) on our top level domain so that we can push out DNS updates within five minutes. Unfortunately, this is not 100% reliable: some ISPs do not enforce these low TTL values because they require more frequent fetching. Users of such ISPs resultantly see longer downtime than everybody else. Users whose ISPs react properly receive correct IP addresses within five minutes from when we push an update.

This, combined with our use of Chef, is our best shot at restoring downed services in minutes rather than hours.

### Use Virtualized Hardware, Not Services, to Reduce Risk of Outages

Amazon Web Services can be used either to virtualize raw hardware (EC2 instances with instance storage) or to virtualize core web services (ELB, EBS, RDS, etc.). This weekend's ELB, EBS and RDS failures demonstrate that you are at much greater risk of a service disruption if you use the latter. None of our instance storage EC2 instances suffered outages.

For this reason, at Shareaholic, we've avoided using AWS' proprietary services whenever possible. Instead of using ELB, we run our own [HAProxy](http://haproxy.1wt.eu/) load balancers. This has reliably fixed the problem of visitors getting directed to unresponsive instances when they go down. Unfortunately, it also means that we own the burden of implementing redundant load balancers. We got burned when the AWS API timed out, prohibiting us from reassigning our Elastic IP addresses to our redundant machines. However, we were still able to get our home-grown load balancers back up hours before Amazon resolved its ELB failures.

We've rolled our own MySQL, Redis, MongoDB and Riak for the same reason. We still suffered downtime because we rely on EBS (which is something we'll work to avoid in the future), but our recovery efforts were made easier and more timely by the fact that we manage our data and load balancing stacks in-house.

### Determine in Advance What Risks You're Willing to Take

My post-downtime debrief boils down to one question:

_Knowing what we know now, what engineering work would have been worth doing in advance to mitigate the downtime we just had?_

Usually my answer to this question is "none." This varies by business, but a few hours to a day of downtime per year is often less expensive than the engineering required to avoid it.

### In Conclusion

Amazon Web Services is not one big service that stays up or goes down. It is comprised of many services of varying complexity. By understanding their individual reliabilities, organizations can engineer around many of AWS' shortcomings.

Still, there's no silver bullet. When things do go wrong, the responsibility of recovery falls on you, the AWS customer. By determining in advance what risks you're willing to take, preparing your DNS for faster updates and automating the generation of your infrastructure, you can respond more quickly when you need to.

_Thanks to [Mike Champion](http://graysky.org) and [Kevin Menard](http://nirvdrum.com) for proofreading this post._