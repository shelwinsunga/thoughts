---
title: "Introduction to Distributed Systems"
enableToc: false
date: 2022-11-02
tags:
- Coursework
- 6.824
---

A lot of critical infrastructure out there is built by distributed systems. If you're designing a system, if you can possibly solve it with a single computer, without a distributed system, do that. It's **always** easier that way. Try everything else before a distributed system, because they're not simpler.

## Reasons we use distributed systems
1. Performance: How do I get 1000 computers to give me 1000x the compute?
    - The reason people use lots of cooperating computers is because they need high-performance, and to accomplish that they need parallelism. 
2. Fault Tolerance
    - Have two computers do the exact same thing, if one fails give the task to the other one.
3. Physical
    - Some problems are naturally spread out into space and become inherently physically distributed systems.
    - Two Banks across the country dealing with the transfer of money.
4. Security 
    - Improve security by splitting things between multiple computers, resulting in isolation.



## Basic Challenges

##### Concurrency 

Because distributed systems compute concurrently, you get all the problems that come up with concurrent programming. Complex interactions and weird timing dependant stuff make the world a scary place.

##### Partial Failure

Distributed is hard because with all the different computers in addition to a network, you will have unexpected failure patterns. If you were working with a single computer, it's usually the case that the computer is working, or it's not. A distributed system may have multiple computers not working, or a single computer not working. A part of the network might be down. These result in partial failures.

##### Performance

Though we build computers to obtain high-performance, there's a lot of roadblocks in the way. It takes careful design to get the performance you feel you deserve.








