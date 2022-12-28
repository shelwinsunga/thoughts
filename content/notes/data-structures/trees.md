---
title: "Trees"
enableToc: false
date: 2022-12-25
tags:
- Data-Structures
- Software
---


A tree consists of 
- A set of nodes
- A set of edges that connect those nodes
  - Constraint: There is exactly one path between any two nodes.

In a rooted tree, we call one node priviledged node the root.
- Every node N except the root has exactly one parent, deifned as the first node on the path from N to the root.
- The root is usually depicted as tthe top of the tree (kind of backwards from how we usually think about trees)
- A node with no child is called a leaf.

In a rooted binary tree, every node has either 0, 1, or 2 children (subtrees).

A binary search tree is a rooted binary tree with one additional property: the BST property.

BST property: For every node X in the tree: 
- Every key in the left subtree is less than X's key
- Every key in the right subtree is greater than X's key

Note that there is a difference between a Binary Tree, and a binary search tree. A binary tree is a tree where every node has at most two children. A binary search tree is a binary tree where the BST property holds.

Ordering must be complete, transitive, and antisymmetric. Given keys p and q:
- Exactly one p < q or q < p are true.
- if p < q and q > r, then that implies p < r  

One consequence of these rules : No duplicate keys are allowed in a BST.
- keeps things simple. Most real world follow this rule.

