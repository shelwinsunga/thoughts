---
title: "Load Balancing"
enableToc: false
date: 2023-01-03
tags:
- Scalability
- Software
---

## Scalability
When we deploy a website, we need to put it on a server. Users will send requests to the server, and the server will respond. But if a lot of users send requests at the same time, the server will get overloaded, so we have to think about scalability.

First, let's think about where those servers are.

### Servers

Servers exist in two places:
- 1. The Cloud
- 2. On-Premise - servers inside a company's building

In an on-premise server, the company owns the server, and they can do whatever they want with it. They can install whatever software they want, and they can control the hardware.

Whereas in the cloud, the company doesn't own the server. They rent it from a cloud provider, and they can't control the hardware. They can only control the software. However, this has its own benefits. 

For example, if a company has a lot of data, they can rent a lot of servers, and they can distribute the data across those servers. This is called horizontal scaling. 

The question "How many users can my server handle?" is called the scalability question. It varies at any given time.


### Vertical Scaling

Vertical scaling is when you increase the power of a single server. For example, you can increase the amount of RAM, or you can increase the number of cores. This approach is simple: swapping out a server is easy. But there are still limits.

### Horizontal Scaling

Horizontal scaling is when you add more servers. This is more complicated, because you have to distribute the data across the servers. But it's more scalable. 

But there has to be some logic for deciding what server a user should go on. When a user sends a request to the server, how does it know which server to send the request to? 

### Load Balancer 

This is called a load balancer and the problem is called load-balancing. t's a piece of software that sits in front of the servers, and it decides which server to send the request to. 

How does the load balancer decide? There are many different approaches:

#### Random Choice

We can just randomly choose a server. This is simple, but it's not very efficient. We might end up with servers that are entirely unused. 

#### Round Robin

Send the request to the first server, then the second, then the third, then the first, then the second, then the third, etc.

This is also relatively simple. But it also suffers from inefficiency. Some requests will take longer than others, so some servers will be overloaded, and some will be underloaded.

#### Fewest Connections

Send the request to the server with the fewest connections. This is a good approach, but it still has its drawbacks. Computing the number of connections might be expensive, and it might not be accurate.

All of these problems suffer from one more problem: sessions. 

A session is a connection between a user and a server. When a user sends a request to the server, the server creates a session, and it sends a cookie to the user. The cookie is a small piece of data that the user sends back to the server with every request. Basically, the cookie is a way for the server to identify the user and store information about the user.

So the issue is that if a user sends a request to the server, and the server sends the request to a different server, the cookie won't be sent back to the server. So the server won't know who the user is. 

How do we load-balance in a session-aware way?

### Session-Aware Load Balancing

#### Stick Sessions

The load balancer will remember what server the user was connected to last time, and it will send the user to that server. The tradeoff is that the server might be overloaded. There's a difference in utilization between servers.

#### Sessions in Database

Rather than storing the session on the server, we can store it in a database. This way, the load balancer can send the user to the server that has the session.

#### Client-Side Sessions

Store the session with cookies. You can store information about what user is currently logged in. But it can be manipulated - in which case you have some sort of encryption. 








