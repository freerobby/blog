---
comments: true
date: '2010-04-10 22:49:35'
layout: post
title: The Death of MacRuby for iPhone?
categories: [Business, Technology]
---

It's a sad day for iPhone developers who like Ruby.<!--more-->

[MacRuby](http://www.macruby.org/) is a port of Ruby 1.9 that interfaces directly with Apple's OS X Objective C runtime. In other words, it lets Mac developers write Cocoa apps in Ruby. This begs the question: will we ever be able to use MacRuby to write iPhone apps? For the time being, there is one technical hurdle: MacRuby needs garbage collection, and "[garbage collection is not available on [the] iPhone.](http://developer.apple.com/iphone/library/DOCUMENTATION/Cocoa/Conceptual/MemoryMgmt/MemoryMgmt.html)"

Last week, with rumors abound of multitasking in TouchOS 4, I wondered if we'd jump this hurdle. Instead of an answer, MacRuby's path to the iPhone got an even bigger hurdle. It comes in the form of the new iPhone Developer Program License Agreement. Specifically, [section 3.3.1, which for the first time states](http://daringfireball.net/2010/04/iphone_agreement_bans_flash_compiler):

> Applications must be originally written in Objective-C, C, C++, or JavaScript as executed by the iPhone OS WebKit engine, and only code written in C, C++, and Objective-C may compile and directly link against the Documented APIs (e.g., Applications that link to Documented APIs through an intermediary translation or compatibility layer or tool are prohibited).

Analysis rather than text is important here. MacRuby is an internal Apple product, and so Apple could easily make an exception for MacRuby if it wanted to. But Apple isn't going to want to do that

Gruber [writes](http://daringfireball.net/2010/04/why_apple_changed_section_331):

> What Apple does not want is for some other company to establish a de  facto standard software platform _on top_ of Cocoa Touch... If that were to happen,  there’s no lock-in advantage. If, say, a mobile Flash software platform —  which encompassed multiple lower-level platforms, running on iPhone,  Android, Windows Phone 7, and BlackBerry — were established, that app  market would not give people a reason to prefer the iPhone.

This logic has ramifications greater than its stated thesis. It's not that Apple doesn't want "some other company" to establish a higher level language standard; it's that Apple doesn't want _any_ company to do that -- including Apple. The reasoning is the same: if Apple were to allow developers to write iPhone apps using MacRuby (i.e. Ruby 1.9), there would be nothing to stop those apps from being moved to other mobile platforms that also support Ruby.

Update April 11, 2010: After speaking with a couple of other developers about this, I think the above syllogism may not hold. If MacRuby is tied intimately to the operating system such that it literally maps API call to API call, then porting a MacRuby app to another platform would not be trivial. Instead, it would likely require a middle ("higher level") layer, which is already banned by the new section 3.3.1. In this case, native MacRuby apps could be written under the current agreement, and this would not allow such apps to be easily ported to other platforms.
