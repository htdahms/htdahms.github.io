---
title: "Mac Catalyst: Just Add Water"
date: 2019-12-30T21:20:23-04:00
draft: true
---

A few months ago I was fortunate enough to add Mac Catalyst support to a client's existing iOS app. Unfortunately, as Apple had just released Catalyst, documentation was scarce. In this post, I'll briefly discuss some of the issues I ran into, how I fixed them (or worked around them) and what improvements I'd like to see in the future.

* Dependency issues. XCFrameworks
* UI updates to make UX fit MacOS/mouse+keyboard/large screen better.
* Signing issues. Extreme lack of documentation.
* Testing. QA. Everyone has to update.
