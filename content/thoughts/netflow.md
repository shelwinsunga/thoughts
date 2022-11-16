---
title: "Netflow"
enableToc: false
date: 2022-11-16
tags:
- Networking
- Software
---

One of the challenges of managing a network is understanding what's actually going through that network. We have a lot of different protocols buzzing around - HTTPS, SMTP, SFTP, DNS, etc - so how do we answer questions like how much of each protocol is happening? Who are the top talkers? What are the most visited destinations? 

# Lights, Camera, Action!
This is where Netflow improves our mortal lives. If you want to monitor your network traffic and see if there are any anomaliesd -A - worry no further. If you want to just see what your traffic patterns look like - with netflow it's trivial. 

There are three basic ingredients:
- A monitor that looks at network traffic as it passes in and out of an unsuspecting router. This traffic is put cached in memory for a short period of time.
- An exporter that takes the recorded traffic data and puts it into a network management system
- A collector that runs on the network management system to visualize the data.  