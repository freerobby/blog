---
layout: post

title: "Practical Off-Grid Solar at Home"
date: 2018-11-30 10:00
comments: true
---

In the last five years, I've been on a mission to cut fossil fuels out of my life. As a result, I have a lot of electrically powered devices for which most people still use gas equivalents: a motorcycle, a snowblower, a lawnmower, a weedwacker, a hedge trimmer, a chainsaw, a leaf blower, and a wood chipper. I've also got a bunch of more typical electric tools: saws, drivers, grinders, and Dremels, etc. All of these items live in my off-grid shed, and need power to charge or operate.

If my shed were adjacent to my house or an outdoor electrical panel, I could probably have dug a small trench and run an underground line for $1k-$2k. But in my case, this would have required a wire run of over 100', removing and repairing asphault, and installing a third subpanel. The price tag was discouraging.

This post details how I solved this problem sustainably and cost-effectively, keeping everything 100% solar powered while mitigating several constraints that were working against my use case:

* My shed sits in the shade for most of the year.
* I live in the northeast, where temperatures stay below freezing for extended periods (it's very bad for Lithium Ion batteries to charge them in such conditions).
* High-efficiency panels, controllers, and converters are very expensive, but I don't get enough sunlight to use cheaper variants in a traditional configuration.

Looking back, what I am most proud of in this system is its simplicity:

* It is entirely modular (any single component can be replaced without negatively impacting the others).
* I did not have to build anything proprietary -- all parts are available locally and/or at Amazon.
* Anybody can use it -- the implementation details don't meaningfully impact how power is consumed. When my wife wants to take out the lawnmower, "it just works."

I expect that as time goes on, more and more tools and devices will transition to electric, and more and more people will want electricity in off-grid facilities.

## Summary

* This project cost $1200.
* I built it in one day (not including construction of the shed).
* I can generate about 1.5 kWh on a good day, and reliably store 760 Wh of it (those are real world numbers -- theoretical is much higher)

I was able to solve my problem, in spite of my shed being heavily shaded, for about $1200. Here's how.

## First Order Constraints

This project began with two questions to determine whether the idea was tenable:

* How much energy do I need?
* How much energy can I capture?

The answers to these questions determine:

* Is the energy I can capture more than the energy that I need?
* If so, what level of efficiency do I have to work with?
* What is the most cost effective way to work within that efficiency?

### Doing the Math: What do I need?

On any given day, I must be able to do one of the following:

* **Add 5 miles to my motorcycle**. I ride 2-3 days/week for local errands. Each mile consumes about 130 Wh, so I need to be able to add about 650 Wh to replenish the battery after its use.

* **Perform cordless yardwork**. The most energy-consuming example is my snow blower, which in heavy snow consumes 85% of two Ego 56V/7.5Ah batteries. This works out to be 714 Wh. 

* **Perform corded yard or wood work**. High-draw applications include running a 120V/12A wood chipper for 20 minutes (480 Wh) or a 120V/15A table saw for 10 minutes (300 Wh). 

* **Perform cordless wood/house work**. Worst case, this requires recharging three 12V/5Ah batteries (180 Wh total).

The most energy intensive application is the cordless snowblower, which requires 714 Wh of stored energy to replenish, after charging losses.

The most power intensive application is a 15A wood chipper, which requires an inverter capable of delivering 1800W continuously. This is equivalent to what most household wall sockets provide.

### Problems With a Typical Setup

A generic off-grid solar setup looks like this:




## Applications

* Shed
* Detached garage
* DIY Home Solar (non grid-tied)
 

There are too many  variables (company stage, company valuation, employee experience, employee domain knowledge, employee salary requirements), let alone disagreement among industry veterans[^fair-equity], to generalize how much equity you should get and when, but Babak Nivi put together a [table of option grants](http://venturehacks.com/articles/option-pool-shuffle#market) that rings true based on my experiences:


[^fair-equity]: I love Joel Spolsky's [approach to divvying equity](http://answers.onstartups.com/questions/6949/forming-a-new-software-startup-how-do-i-allocate-ownership-fairly/23326#23326), but it is a minority opinion.
