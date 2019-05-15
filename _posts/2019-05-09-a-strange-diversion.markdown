---
layout: post
title:  "TDD - Test-Driven-Drivel"
date:   2019-05-09
categories: [software, engineering]
comments: true
---

I recently reviewed a pull request for a new feature for our microservice. The microservice has a dependency on a third party api, and the feature is to make use of an additional capability of that api. It was straightforward pull request, the api client was expanded to include additional request payload, there were unit & integration tests, stubs, some documentation. 

All good, but what I noticed was that the implementation code change constituted circa 20% of the pull request, the rest was test code. And I've noticed this trend for a few years in my recent career. Espousing TDD and 100% code coverage has somehow lead us into this perverse scenario where we've gone from perhaps 50% parity with actual code to the situation where test code has bloated and taken the lions share of code cross-section.

This has a few problems, test code is code, and suffers from the same problem of refactoring, readability, SOLID, bugs. Also if you favour implementation style tests, this can lead to brittle test code that breaks upon any refactoring in the implementation. This problem is exacerbated when you have more test code than implementation code.

As I eek ever closer toward pragmatism I'm seeing less and less utility in tests for the sake of tests. There is an argument that if a test never breaks, what is the utility of said test? That is certainly common at solution inception, where TDD will drive a lot of the infrastructure, this effectively 'scaffolding' your app. Once the infrastructure is in place, it barely moves and thus the tests almost never go red. At this point there is an argument for throwing those tests away.

`Aside:` I'm a big fan of testing behaviour over implementation. There are [numerous articles](https://www.google.com/search?q=testing+implementation+and+behaviour) discussing the merits of both. Essentially you treat your entity as a black box and assert the inputs vs outputs (and thus behaviour) of the entity, without much care of the internal implementation details. You are then free to refactor the implementation details without having to refactor your tests in step.

Summing up, I think we as engineers need to take a step back and consider the bigger picture. I'd rather have a handful of really well thought-out, easy to read tests than a smattering of tests in the endeavour to achieve 100% test coverage.
