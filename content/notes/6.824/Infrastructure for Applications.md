---
title: "Infrastructure for Applications"
enableToc: false
date: 2022-11-02
tags:
- Coursework
- 6.824
---

A lot of our goal is to discover **abstractions**, or ways of simplifying the interface of distributed storage and infrastructure so that it is easy to build applications on top of it. We want to *hide* the fact the system is distributed.

# Implementation 

1. Remote Procedure Call (RPC)
    - Mask the fact you're communicating over an unreliable network.

2. Threads
    - A way of structuring concurrent operations so that the programmer lives a happier life.

3. Concurrency control
    - We'll need to spend a certain amount of time thinking about this.

## Scalability

Usually the high-level goal of building a distributed system is to build something with scalable speed-up. It's the idea that with 2 times the computer resources, I should get 2 times the throughput. The alternative is to pay programmers to restructure your software. 


