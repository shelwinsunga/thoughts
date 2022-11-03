---
title: "Anatomy of a Production App"
enableToc: false
date: 2022-11-03
tags:
- Software Architecture
- System Design
---

# Application Architecture

Developers need to write code which needs to get deployed somewhere. Eventually, that code will reach some server to run on. A server is a computer that can handle requests, serving users. Usually building happens on a CICD server in the production world. 

The server will need to store some data. Usually the storage is running on a different server and is connected on a network, via distributed systems. 

A user will need to send a request to the server, and our server needs to respond. 