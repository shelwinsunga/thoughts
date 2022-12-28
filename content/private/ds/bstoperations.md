---
title: "BST Operations"
enableToc: false
date: 2022-11-16
tags:
- Networking
- Software
---

# Search

If searchKey = T.key, return.
- If searchKey < T.key, search T.left;
- If searchKey > T.key, search T.right;

Runtime to complete search on a bushy BST in the worst case is $O(log_2(n))$. This is intuitive to see and you can generally estimate the number of computations needed to search a BST by the height of the tree.\

Remember, the height of the tree is roughly $log_2(n)$. So if the tree is 15 nodes, $log_2(15) = 4$. So the worst case runtime is $O(4) = O(1)$.

Bushy BSTs are extremely fast.

At 1 microsecond per operation, can find something from a tree with $10^300000$ in one second. 

Much (perhaps most?) computation is dedicated towards finding things in response to queries. 

# Insert 

Search for key. 
- If found, do nothing.
- If not found 
  - Create a new node
  - Set appropiate link. 

