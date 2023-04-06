---
title: "Computer Architecture"
enableToc: false
date: 2023-04-04
tags:
  - Systems
---

## A high level overview of how computer architecture

### Disks and RAM

We'll start with the disk.

Disks will store all our data (SSD, HDD) persistently. Writing and reads are measured in milliconds $(ms)$.

We also have **RAM** (random access memory), which is a lot smaller. However, it's quite fast - writing and reading to it is measured in microseconds $(\mu s)$.

RAM is an order of magnitude faster than disks.

### CPU

How do we write/read our disk and RAM? What if we wanted the disk and RAM to communicate with each other?

Here we introduce **CPU** (Central Processing Unit). When we talk about read or write speed, we talk about how fast the CPU can write or read. The CPU really only knows how to do computations - arithmetic, logical, bit, etc.

### Cache

While we know that the CPU can write to RAM in terms of microseconds, we can go even faster. Introduce the cache, which is measured in megabytes (so, considerably smaller than RAM). Its primary job is to make reads and writes to RAM faster. It takes a subset of the data in RAM and stores it in the cache, so that when we want to read or write to RAM, we can do it 10 or 100 times faster.

The drawback of cache and RAM is persistence: if we turn off the computer, all the data in the cache and RAM will be lost. So we need to store it somewhere else (the disk).

This is a high level overview of how computers, and when it comes to designing distributed systems, we'll find parallels from how a single computer works to how a distributed system works.

One of the bottlenecks is CPU - how fast we execute our code. Moore's law says that every 2 years, the number of transistors on a chip will double. However, this is plateauing, and we're seeing diminishing returns.

We can solve bigger problems by using more computers.
