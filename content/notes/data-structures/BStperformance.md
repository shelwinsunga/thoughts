---
title: "BST Performance"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

Height and average depth are important properties of BSTs:
- The depth of a node is how far it is from the root
- The height of a tree is the depth of its deepest leaf
- The average depth of a tree is the average depth of a tree's nodes.

$$ \text{Average Depth} = \frac{\text{Total Depth}}{\text{Number of Nodes}} $$  

Adding in linear order will result in a spindly tree. Adding in random order will result in a bushier tree.

We now know and have seen in great detail is that 
- the worst case is $\Theta(n)$
- the best case is $\Theta(log(n))$

Random trees have an average depth of $\Theta(log(n))$. In other words, random trees are bushy, not spindly.

# Mathemetical Analysis

The average depth of a tree is $ ~2log(n) = \Theta(log(n))$. The tilda (~) is can kind of be thought of as $\Theta$ but we don't drop the constant. Thus the average runtime for `contains` is $\Theta(log(n))$ on a tree built with random inserts.

If $N$ distinct keys are inserted into a BST in random order, the expected height of the tree is $~4.311log(n)$. This is beyond the scope of this text (the proof was made in 2003).

# Bad news

We can't always insert our items in random order. This is because Data comes in overtime! We don't have it all in advance. If you're storing a bunch of dates, your binary tree will be horrible. 





