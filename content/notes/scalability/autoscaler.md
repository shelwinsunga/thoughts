---
title: "Autoscaling"
enableToc: false
date: 2023-01-09
tags:
- Scalability
- Systems
---

## How many servers do we need

We can use benchmarking here - extrapolating based off how many users one server can handle. But it might be the case that our user count fluctates (as in the case of a newspaper website), so we can't just use one number.

In this case, let's consider the maximum. So that no matter how many users we get, we can handle it. But even in this case, it's still not the most economical choice. In the vast majority of cases, we'll have too few users, and we'd still be paying for the servers - electricity, maintenance, etc.

## Auto Scaling (Cloud)

One solution to this is **autoscaling**. The load balancer will automatically add or remove servers based on the number of users. Often, there is a minimum and maximum number of servess that can be configured and which can be scaled up or scaled down. There are tradeoffs here too, where it will take time for the autoscaler to add or remove servers. If a lot of users come at once, the autoscaler might not be able to keep up, or service them immediately. 






