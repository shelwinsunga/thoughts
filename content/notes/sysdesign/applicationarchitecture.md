---
title: "Application Architecture"
enableToc: false
date: 2023-04-04
tags:
  - Systems
---

## A high level overview of Application Architecture

There are two perspectives to consider when it comes to application architecture: the developer's and the user's.

### Developer's Perspective

The developer is going to write some code. This code will be built and deployed to some server. The server is going to need to write and read from some storage system - a database is probably the first thing you're thinking of. note that the storage system does not run on the server, but is connected over some kind of network.

A server is anything that can handle requests, so that when a user makes a request to the server, it can respond with everything it needs to: the html, javascript, images, and other files. The server is going to have a CPU which will compute the response it needs to give to the user. But if there are a lot of requests - imagine millions of users requesting to the same server - the CPU won't be able to keep up. You can think of a chef: a single skilled chef will be able to serve a some amount of people. I struggle to think of a number, but say a family or two at a time. But if the entire town decides it wants food - well - no matter how skilled you are, you are not serving everyone.

If you were Gordon Ramsey, you might be able to serve more people than most Chefs. Instead of a family or two, it might be twice that. In the same way, you can have a faster CPU, and this would improve the number of people that can make requests to your server. This is called vertical scaling: making your server more powerful.

But unless you're rocking a million-core quantum CPU, you're not going to serve much more. So we need more computers - more CPUs. This is called horizontal scaling: adding more servers. This is the most common way to scale a server. You can have a single server, or you can have a cluster of servers. A cluster is a group of servers that work together to serve requests. You can have a cluster of 2 servers, or 100 servers. The more servers you have, the more requests you can serve.

Having multiple servers introduced a new problem: which server does the user's request go to? That's where load balancing comes in.
