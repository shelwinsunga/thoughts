---
title: "Design Requirements"
enableToc: false
date: 2023-04-06
tags:
  - Systems
---

## Design Requirements

At a high level, we are ultimately just moving data, storing data, and transforming data.

In larger systems, data moves between data centers (through the network). We also care about how we store data.

Large data needs to be stored in an efficient way.

We also need to transform data. Maybe we want to figure out what percent of logs are successful, and what percent fail.

Bad design choices are very difficult to correct later.

What is a good design?

- Availability (generally)

A 1% downtime to 0.1% downtime is a 10x improvement.

Availability us used to define SLO (Service Level Objectives). As an aside, there's also SLA (Service Level Agreements) which is a contract between a service provider and a customer.

An example of an SLO is "99.99% of the time, the service will be available". This is a very high availability, and is generally not achievable. And SLA is a contract that says "if the service is not available 99.99% of the time, we will give you a refund".

- Reliability

Reliability is the probability that our system won't fail.
