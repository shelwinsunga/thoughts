---
title: "BST Tree Height"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

Height varies dramatically between "bushy" and "spindly" trees.

- Bushy trees have a height of roughly $log(n)$.
- Spindly trees have a height of $n$.

This means that for a bushy tree, we have to double the number of nodes to increase the height by 1. For a spindly tree, we have to add 1 node to increase the height by 1. 
- Performance of operations on a spindly tree can be just as bad as a linked list.

Importantly, Big-O and Theta notation are different. Big-O is less precise, and can be analogus to an inequality. If I say that a Binary Tree's height is $O(n^{2})$, what I'm saying in english is

> The height of a binary tree grows less than or equal to n^{2}

This is still true.

Whereas, if I say a binary tree's height is $\Theta(log(n))$, what I'm saying in english is

> The height of a binary trees grows equal to $log(n)$ in the best case ($n$ in the worst case).

Note that Big-O is still useful. In the real world, Big-O is shorthand for "in the worst case". 
- It allows us to make simple blanket statements
- Sometimes we don't know the exact runtime, so we use Big-O to give an upperbound
- It can be easier to write proofs for Big-O than Big-Theta.




