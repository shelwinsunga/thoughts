---
title: "Red Black Trees Performance"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---

# LLRB Runtime

- LLRB has height $O(log(n))$
- Contains is trivially $O(log(n))$
- Insert is $O(log(n))$
  - $O(log(n))$ to add new node
  - $O(log(n))$ to fix up tree (rotation and color flips)

We won't discuss delete because it's uninteresting.

#  Summary

- BSTs are simple, but they are subject to imbalance.
- 2-3 Trees (B-Trees) are balanced, but are painful to implement and are slow.
- LLRBs insertion is simple to implement (but delete is hard).
  - Works by maintaining a mathematical bijection with 2-3 trees.
- Java's TreeMap is a red-black tree (not left leaning).
 - Maintains correspondence with a 2-3-4 tree (is not a 1-1 correspondence).
 - Allows glue links on either side
 - More complex implementation, but significantly (?) faster.

# Footnote

There are many other types of search trees out there. AVL trees, splay trees, treaps, etc. 
- And there are other efficient ways to implement sets and maps entirely.
    - Skip lists
    - Hashing (the most common alternatives)
