---
title: "Tree vs Graph Traversals"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---

Just as there are many tree traversals:
- Preorder
- Inorder
- Postorder
- Level Order

## DFS Preorder

What we did in DepthFirstPaths is called "DFS Preorder": Action is before DFS.

In a graph, we choose a particular source. We also have to decide how to deal with "tie-breaking".

## DFS Postorder

We could also do a "DFS Postorder" traversal, where our action is after the DFS.

example:

`dfs(s)`: 
- mark s
- for each unmarked neighbor `n` of `s`, `dfs(n)`
- print s

This would print the nodes in order of dfs returns. 

These are analogs to the tree traversals. There is also an analog to level order traversal.

# BFS order
BFS stands for Breadth First Search. 

BFS Order: Act in order of distance from source.
- Analogous to level order traversal
- Search is wide, not deep
