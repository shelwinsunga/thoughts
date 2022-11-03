---
title: "System Scalability"
enableToc: false
date: 2022-11-02
tags:
- Coursework
- 6.824
---

Usually the high-level goal of building a distributed system is to build something with scalable speed-up. It's the idea that with 2 times the computer resources, I should get 2 times the throughput. The alternative is to pay programmers to restructure your software. To get more performance, you can either buy more compute, or better programmers. Compute is cheaper, so more ideal.

## Got a website?

When you host a website, it runs on a web server and has a database attached to it. To add more compute so that more users can visit your website, you add more web servers. This kind of scalability is rarely infinite, and as you add more web servers, suddenly the database has too much pressure. 