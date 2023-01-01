---
title: "Priority Queue"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---

A priority queue allows tracking and removal of the smallest item.

the interface;
- `add`
- `getSmallest`
- `removeSmallest`

It can transform a problem which requires a lot of memory into one which requires much less. 

# Implementation

We could use an ordered array, but adding and removing elements would be $O(N)$. We could also use a bushy BST, and for add, removr, and getSmallest, we would have $O(\log N)$ time. The issue is the possibility of duplicates, which is very awkward to implement/fix (though possible!). We could also use a hash map, and adding would be $O(1)$, but removing and getting the smallest would be $O(N)$ because we don't know what bucket the smallest item is in.

So what we need is a heap. It will give us $O(\log N)$ for all operations, and it will also allow duplicates.

