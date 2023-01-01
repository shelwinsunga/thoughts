---
title: "Heaps"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---

Heaps are a pretty famous data structure. Note that they're not at all related to 'the heap', something you'd learn in an operating systems class.

# Introducing the Heap

It is a binary tree with the following properties:
- It is a complete binary tree (all levels are filled except the last, which is filled from left to right)
- It is a heap-ordered binary tree (the key in each node is larger than the keys in its children)

# Heap Operations

## Insert

- Add the new node to the bottom level of the heap, as far left as possible
- Swim the new node up until it is larger than its parent, or it is the root

## Delete Smallest

- Swap the root with the node at the bottom level, farthest right
- Sink the new root down until it is smaller than both of its children, or it is a leaf

## Get Smallest
- Return the root