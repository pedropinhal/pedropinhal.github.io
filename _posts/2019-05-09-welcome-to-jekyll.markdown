---
layout: post
title:  "A strange diversion!"
date:   2019-05-09 22:32:31 +0100
categories: jekyll update
---

I recently reviewed a pull request for a new feature for our microservice. The microservice has a dependency on a third party api, and the feature is to make use of an additional capability of that api. It was straightforward pull request, the api client was expanded to include additional request payload, there were unit & integration tests, stubs, some documentation. All good, but what I noticed was that the actual code change constituted circa 20% of the pull request, the rest was test code. And I've noticed this trend for a few years in my recent career. Espousing TDD and 100% code coverage has somehow lead us into this perverse scenario where we've gone from perhaps 50% parity with actual code to the situation where test code has bloated and taken the lions share of code cross-section.

I'm a big fan of testing behaviour over implementation.

This has a few problems, test code is code, and suffers from the same problem of refactoring, readability, SOLID, bugs. Also if you favour implementation style tests, this can lead to brittle test code that breaks upon any refactoring in the implementation. This problem is exacerbated when you have more test code than implementation.