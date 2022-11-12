---
title: "Netflow"
enableToc: false
date: 2022-11-12
tags:
- networking
- software
---

One of the challenges of managing networks is understanding what's actually going through them. There are a bunch of different protocols - HTTPS, DNS, SMTP, ICMP, etc - but how much HTTPS is there compared to say, SFTP? Is it 10% more? 30% more? Who are the top talkers on our network? What are the most frequent destinations? For this we use netflow.

Different people have different reasons to use netflow. Maybe we just want to understand how much traffic we have and if there are any anomalies.  