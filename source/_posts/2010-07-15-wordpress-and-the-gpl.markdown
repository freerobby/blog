---
comments: true
date: '2010-07-15 11:23:08'
layout: post
title: Wordpress and the GPL
categories: [Business, Technology]
---

Yesterday, [Wordpress](http://wordpress.org/) founder [Matt Mullenweg](http://twitter.com/photomatt) [debated](http://mixergy.com/chris-pearson-matt-mullenweg/) [Thesis Wordpress Theme](http://www.diythemes.com/) founder [Chris Pearson](http://twitter.com/pearsonified) over the ethics, legality and benefits of using the GPL license for the Thesis theme. Matt argued that by not using the GPL license, Thesis is disrespecting the Wordpress community, violating the Wordpress license agreement and hurting its own business. Chris contends that Matt has no right to tell him how to license something that Chris built himself, even though he built it on top of the Wordpress platform.

I'm not an attorney, but I am a human capable of reading and inferencing. The legal issues concerning the GPL seem pretty clear to me. There's a reason why Dan Rivcher is [cited](http://www.linux.com/archive/articles/113252) by the Software Freedom Law Center's [compliance guide](http://www.softwarefreedom.org/resources/2008/compliance-guide.html). There's a reason why the SFLC [sides with Wordpress](http://wordpress.org/news/2009/07/themes-are-gpl-too/). There's a reason why lawyers at big companies tell their engineers not to use GPL open source projects. There's a reason why the LGPL exists. There's a reason why many communities, like the Ruby community, have moved to use the MIT license instead of the GPL. All of these reasons are the same: the GPL is a highly [viral](http://en.wikipedia.org/wiki/GNU_General_Public_License#Criticism) license that infects everything it touches. If your code uses GPL, your code needs to be GPL. I don't know this because I'm a lawyer; I know it because every credible lawyer I talk to or read about or am influenced by reaches the same conclusion.

And I'm reminded of how well I know this, because I gave up healthy means of income in order to abide by it.<!--more-->

## My Experience with the GPL

The GPL gave me my first headache when I was in college. I was building [my mother's blog](http://www.hudsonvalleypainter.com), which required me to build what became [ArtPal](/artpal), a Wordpress plugin that lets artists post their work to their blogs and sell it with PayPal. Today, ArtPal is fairly popular for a niche plugin. It has 3,000+ downloads from artists all over the world who use it to sell their paintings, drawings, sketches and digital compositions. A modest estimate would have it responsible for hundreds of sales.

What is my cut? $0, thanks to the GPL. I say this without vent or complaint. I have no regrets about ArtPal being free, and I'm thrilled (really! I get a warm fuzzy feeling!) to know that the hard work I put in for my mother is helping tens or hundreds of other artists to sell their work online. I point out the following merely to explain how the GPL license can undermine the business worthiness of a technical venture.

I started out by retaining the full rights to ArtPal under the name of Digital Sublimity, the corporate outfit I used for my consulting work. I let myself live in denial, trying to convince myself of the argument that Chris Pearson put forward yesterday. "It's its own thing; it just adds functionality to Wordpress," I would assure to myself. "ArtPal was _my_ innovation, not Automattic's." I felt I had an ethical, exclusive right to own my product, and I did not accept that the legal terms of the GPL might preclude that.

But some time after my first client, my intellectual curiosity won out. I read the GPL, did some googling, and accepted the truth. ArtPal integrates with and requires Wordpress to function. That makes it a "derivative work" of Wordpress, which is also GPL licensed. Consequently, I must apply the GPL license to ArtPal. From this point on, ArtPal was open sourced and formally GPLed. Doing this did not prevent me from selling ArtPal, but it did give others permission to give ArtPal away for free. It doesn't take a strong economics background to see the problem I quickly faced. While it made good resume candy, I never made another dime off of the plugin.

Common questions I get when I tell this story include "Did it ever bring you money in other ways? Did it ever get you new clients? Did anybody pay for support?" No, no and no. I tried. I advertised ArtPal as being commercially supported by Digital Sublimity and referred people there if they ever wanted it customized. But nobody did. The problem, I suspect, is that I built ArtPal to be simple and easy to set up. Plug in your PayPal email address, choose a "buy it" button, and you're up  and running. If you can install a PHP app on a web host, you can configure ArtPal. If you have a web guy who runs your blog, he can configure ArtPal. An end-user has no need for me. I do answer questions on my [ArtPal page](/artpal) as they come up, but they are never in-depth enough to warrant a paid support contract.

The GPL effectively rendered ArtPal a pro bono project. As a part-time effort, I was unable to make it businessworthy while abiding by the full terms of the license.

## Why the GPL Is Good for Wordpress

You might expect me to be resentful or frustrated given the aforementioned story, but I have no beef with Automattic for choosing the GPL license for Wordpress. I would probably have made the same decision if I were Automattic.

By GPLing Wordpress (and therefore its plugins and themes), Automattic ensures that any Wordpress user can get up and running with all the community has to offer, for free. A user may need to pay for support or for customization, but they can get any plugin or theme out of the box for $0, because the GPL stipulates a number of things that make such content freely available. This effectively lets Wordpress outsource the development of thousands of features to its developer community for free.

Less obviously but more importantly, it commoditizes plugins and themes, which are [complementary goods](http://en.wikipedia.org/wiki/Complementary_good). Joel Spolsky [famously wrote about](http://www.joelonsoftware.com/articles/StrategyLetterV.html) this business practice known as "commoditizing the complement." More recently, Chris Dixon [called out](http://cdixon.org/2009/12/22/google-should-open-source-what-actually-matters-their-search-ranking-algorithm/) Google for disingenuously using the same strategy. For those who aren't familiar, here's what "commoditizing the complement" means for Automattic: a blog platform + theme + plugins + hosting is worth $x to a customer. By making plugins and themes free, more of that x can be captured under "blog platform" and "hosting." Not coincidentally, "blog platform" and "hosting" are the things that Automattic sells at wordpress.com.

The GPL lets Automattic outsource development efforts for free while capturing a bigger piece of the pie.

## What the GPL Meant for Me As a Wordpress Developer

The GPL limits occasional Wordpress developers like myself to service-oriented businesses. Charging for a plugin is not practical, but charging for a customization is. Designers may find themselves in similar situations where they cannot realistically charge for a stock design, but they can charge to custom-tailor it for a client.

One might argue that this provides a disincentive to develop plugins. Why spend all that time building it if somebody else can customize it and earn the money off it? The business counter-argument is reputation. ArtPal created a lot of possibilities for me. When I did Wordpress consulting, people had an immediate trust in my work because (1) they knew I built it and knew how to tweak it; (2) I had a strong online presence with a reputation for backing what I built; and (3) I had personal interactions with many of them in the comments section of my blog.

I never capitalized on any of this. The projects that people wanted me to do were too involved for what I had time for. Nobody wanted to pay me just to set up ArtPal; they wanted to pay me to set up, maintain and monitor an entire blog. But for me ArtPal was just a side project, and with a full time job I didn't have time to be a tech support guy for all of the people who wanted to use it.

ArtPal was too small of a project to be made into a business under the GPL. But had I wanted to create a bigger business, ArtPal would have opened the doors to a larger client base.
