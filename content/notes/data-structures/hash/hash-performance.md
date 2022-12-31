---
title: "Hash Performance"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---

Unfortunately, the hash table we devised is $O(Q)$ for its operations, and $Q$ has $O(N)$ order of growth.      

This is really bad, because eventually our operations will get slow.

We can fix this by adding more buckets!

# Model

Suppose we have:
- M buckets
- An increasing number of $N$ items.

An example strategy: When $\frac{N}{M}$ is $\geq$ 1.5, then double M.
- $\frac{N}{M}$ is known as the `load factor`. It represents how full the hash table is. 

As long as $M = \Theta(N)$, then $N = \Theta(\frac{N}{M}) = O(1)$.

One thing to note is that when we do our resizing, items in our table will shuffle around and the lists will get shorter. 
- Resizing takes $O(N)$ time.
- Most `add` operations will take $O(1)$ time. Some will take $O(N)$ time to resize.
-  Also, the specific load factor constant doesn't matter. We will still get $O(1)$ time.


More specifically, with resizing, `contains` ia $\Theta(1)^{†}$ and `add` is $\Theta(1)^{* †}$. `†` means that we assume items are evenly spread, and `*` means "on average".

