---
title: "Red Black Trees Intro"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---

> "Beautiful algorithms are, unfortunately, not always the most useful." - Donald Knuth

B-Trees are painful to implement. And even if you do implement them, they're still not that great. They're $O(log(n))$, but there are better $O(log(n))$ data structures out there.

Some of the things that make it painful:

- Maintaining different node types.
- Interconversion of nodes between 2-nodes and 3-nodes
- Walking up the tree to split nodes.

# The idea

In a normal BST, we can get different BSTs depending on our insertion order. 
- In general, for $N$ items, there are [$\textnormal{Catalan}(N)$](https://en.wikipedia.org/wiki/Catalan_number) different BSTs.

But given any BST, we can move to a different configuration using a rotation. 

Rotation definition: A rotation is a transformation of a tree that preserves the BST property.
Example: A left rotation on a node $x$ is a transformation that moves $x$'s right child to $x$'s position, and moves $x$ to $x$'s right child's position. 

We can shorten (or lengthen) a BST by performing a rotation. There is a paper proving we can do an optimal set of rotations in $O(n)$. 
 


