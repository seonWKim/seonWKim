---
title: "Building a Side Project: Where to start"
date: 2025-04-289T00:21:05+09:00
categories:
  - blog
tags:
  - SpringBoot
  - ActorModel
  - SideProject
  - Pekko
  - Java
---

The most thrilled(or boring) part when starting your side project is choosing the name of your project. Because I'm
trying to glue between spring and the actor world, I can simply use names such as

- spring-boot-actor-starter
- spring-boot-pekko-starter

But I don't want to confine this project to pekko, so the first naming might be more appropriate.

Now that I've choose the name, we should choose which features to implement first. The most important thing is to build
an adaptor layer so that our users using spring boot can utilize actors better. Should I start with supporting pekko? Or
should I allows users to choose between different actor models? Then I should provide an abstraction layer for the actor
model, but isn't it an overkill for my MVP version? Maybe I can start with pekko first, and after I've had gained enough
experience with the actor model, I could start to add more stuff.