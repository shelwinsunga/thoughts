---
title: "B-Tree"
enableToc: false
date: 2022-12-28
tags:
- Data-Structures
- Software
---

B-Trees are a kind of self-balancing BST. 

# B-Trees

To start, let's make a rule to never add a new leaf. Instead, we'll just add any new value to a node.

But this node can get quite big, and our data structure will degenerate to a linked list. That's no good. Instead, let's set a limit $L$ on the number of items
that can be stored in our node. 

- If a node has more than L items, give an item to parent.
- Point parent to new node that was split off.

Examining a node costs us $O(L)$ compares, but that's fine since L is constant.

# What if we split non-leaf nodes?

- Observation: Splitting-trees have perfect balance. 
  - If we split the root, every node gets pushed down a level.
  - If we split an internal node, the height doesn't change. 

# Terminology

Splitting Trees are B-Trees. B-Trees of order $L = 3$ are called 2-3-4 trees or 2-4 trees. 
- B-Trees trees of order $L = 2$ are called 2-3 trees. 
- The "2-3-4" refers to the number of children a node can have. For example, a 2-3-4 tree has 2, 3, or 4 children.


Note that the origin of the name "B-Tree" is unclear. "Broad", "Bushy", and "Balanced" are all possible explanations. The most likely one is "Bayer", since the first paper on B-Trees was written by Bayer.

# B-Trees in Practice

- B-Trees are used in databases and file systems. L would be very large (in the thousands).
- Conceptually simple balanced search tree.







