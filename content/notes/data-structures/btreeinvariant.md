---
title: "B-Tree Analysis"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---

# Bushiness and Invariants
Unlike in BSTs, where if you insert things in order the tree will be spindly, in B-Trees, if you insert things in order, the tree will be bushy no matter what.

We get two nice invariants:
- All leaves are the same distance from the source
- A non-leaf node with $k$ items must have $k+1$ children

These invariants guarentee a bushy tree.

# Runtime Analysis

Let's analyze the runtime of a `contains` operation.
- In the worst case, we're going to need to check $H+1$ nodes, where $H$ is the height of the tree.
- In the worst case, we're going to need to check $L$ items in each node.

This means our runtime will be $O((H+1)L)$ which is $O(HL)$.

However, we know that $H = \Theta(log(n))$, so $O(HL) = O(Llog(n))$ = $O(log(n))$. Note L is a constant, so we can drop it.

