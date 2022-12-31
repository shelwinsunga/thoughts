---
title: "Hashing Collisions"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

Pigeonhole principle tells us that collisions are inevitable due to integer overflow.
- hash code for "moo" and "nep" might both be 718.

The way we deal with this is creating "buckets" where a collision may occur. This can look like anything; linked lists, arraylists, etc. 

That means the runtime for `contains` and `insert` will be $O(Q)$ where $Q$ is the length of the longest list. 

One more innovation: We don't need billions of buckets or indexs. We can reduce them. For example, if our hash code is 123109, we can apply `% 10` to get 9.

This is basically what a hash table is.

# The pipeline

We start with something we want to store, say the word 'hi', inside the hash table. We then compute the hash code using a hash function. We reduce the hash code in some way, and store it at that index. 

