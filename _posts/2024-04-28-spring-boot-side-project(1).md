---
title: "Building a Side Project: Blending Spring and the Actor Model"
date: 2025-04-29T00:00:00+09:00
categories:
  - blog
tags:
  - SpringBoot
  - ActorModel
  - SideProject
  - Pekko
  - Java
---

Recently, I’ve been busy with work, and I ended up putting off my side projects. I started feeling like I was
losing the real happiness that comes from learning something new outside of my job. I really wanted to make
something useful (there MUST be a NEED) and regain the joy that comes from programming.

In South Korea, most companies use Java with Spring (usually Spring Boot). Modern programming guides recommend
building stateless architectures. So yes, we mostly use Spring MVC (or WebFlux) to build our web servers. But
sometimes, I’ve struggled when architecting applications that need stateful features. Think about chat apps —
your server needs to know where the clients inside the same chatroom are located. Otherwise, you can’t send
messages between them. In stateless applications, you have to find a way to make it stateful. For example:

- Using a message bus like Redis pub/sub, NATS.io, or Kafka.

Sure, building that kind of system is fine at big companies. But what if you want to build it as a side project
using familiar tech like Spring Boot? Do you really want to introduce a whole message bus into your
architecture? (Especially when your server handles only a small number of requests — or even none?)

There’s a well-known programming model suited for stateful applications: the actor model.

I’ve heard about it here and there:

- The Akka framework
- The Elixir programming language
- Big tech and telecom companies

I became pretty interested in the way they model things:

- Encapsulate logic into actors
- Communicate by sending messages between them

It felt much more intuitive, especially from an OOP (Object-Oriented Programming) perspective. With Spring Boot
and plain Java, I always had to be careful not to break encapsulation and OOP best practices. But with actors,
just following their programming style naturally keeps you within good OOP principles. Beyond that, actors make
clustering across stateful applications much easier.

The actor model isn’t a silver bullet either. (If it were, wouldn’t it be used everywhere?) But if I can
integrate the actor model with Spring, maybe I can bring together the good parts of both worlds. (Yeah, it could
also bring the worst parts too — who knows.)

Here's the rough plan:

- Build a library that integrates Spring and the actor model.
- Not build the actor system from scratch.
- Instead, use Pekko — an open-source, community-driven fork of Akka without licensing headaches.

Pekko has already been battle-tested in many real-world systems, so it feels like a solid choice.

Starting a new side project is always exciting. But to make it sustainable, it has to be **useful**. While
developing, I’ll stay focused on:

- Being **practical** first
- Optimization and beautiful code will come later — after the working code

Hope I can run a (programming) marathon this time. 
