---
comments: true
date: '2008-01-02 12:44:50'
layout: post
title: Remove My Bluetooth Places from Your Desktop
categories: [Hacking, Technology]
---

If you just installed WDM Bluetooth drivers, you'll find a new icon on your desktop. Unlike the others you've got, this one won't allow you to delete it. Luckily we can remove it with a bit of subterfuge. Here's how.<!--more-->

1. Right click anywhere on your desktop (not on an icon), click "Properties"

1. Click the "Desktop" tab.

1. Click the "Customize Desktop..." button.

1. Click the "Clean Desktop Now" button.

1. Click the "Next >" button.

1. Check the "My Bluetooth Places" checkbox if it is not already checked.

1. Click the "Next >" button.

1. Click the "Finish" button.

1. Click the "OK" button.

1. Click the "OK" button.

Voila!

_Update (2/9/2007)_: User "Oscar" has generously weighed in with these Windows Vista-specific instructions:

1. Run regedit

1. Open HKEY_LOCAL_MACHINE\SOFTWARE
\Microsoft\Windows\CurrentVersion\explorer\desktop\NameSpace

1. Delete 32B4C379-4AC0-45F2-939C-D4E7ADA56DC5 or just check which one is “My Bluetooth Places” and delete it.
