---
title: "Fault Tolerance"
enableToc: false
date: 2022-11-03
tags:
- Coursework
- 6.824
---

See Also: [Scalability](Scalability.md), [Infrastructure for Applications](Infrastructure%20for%20Applications.md), and [Introduction to Distributed Systems](DistributedSystemsIntro.md)

A single computer can often stay up for years. However, if you're building a system with thousands of computers, that means you're going to have about 3 computer failiures per day. Big problems with big distributed systems turn rare failiure problems to failiure problems that happen all the time. There's almost always something broken: a computer crashed, a piece of the network is down, someone stepped over a cable, a fan is overheating - something always goes wrong. 

# Designing around Fault Tolerance

This means that when you're designing a distributed system, you have to bake in the masking or invisibility of these constant failiures. This makes the programmer's life easier. 

Some systems are designed to continue providing, despite partial failiures, undamaged service. These systems are called **available**. The way available systems are specified is that they will stop working after a certain amount of partial failiure.

Other systems will stop working when there are failiures and wait for the failed components to be repaired. But when it does recover, when those components are fixed, the system will continue providing service as if nothing ever went wrong. Systems like these need to do things like save their data on disc. Note available systems can also be recoverable.

## Storage

Non-volatile storage is a good way to keep track of the state of the system. These tend to be expensive to update. 

Another tool is replication. The problem is that the two replicas tend to drift out of sync and stop becoming replicas. 
