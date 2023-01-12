---
title: "Sorting"
enableToc: true
date: 2022-01-01
tags:
- Algorithms
- Software
---

# Sorting 

Informally: Given items, put them in order. This is useful because can do things like:
- Allow rapid duplicate finding
- -Enable binary search
- Convert into various data structures

## Knuth's Definition

An ordering relation `<` for keys `a`, `b`, and `c` is has the following properties:
- Law of trichotomy: `a < b` or `b < a` or `a = b` is true
- Law of transitivity: if `a < b` and `b < c`, then `a < c` is true

An ordering relation with the properties above is also known as a "total order".

A **sort** is a permutation of a sequence of elements that puts the keys into non-decreasing order relative to a given ordering relation.
- $x_1 \leq x_2 \leq x_3 \leq \dots \leq x_n$


## Inversions

We can have an alternate perspective of sorting. An **inversion** is a pair of elements that are out of order with respect to `<`. 

For example, in the sequence $[1, 3, 2, 4]$, the pair $(3, 2)$ is an inversion.

Another way to think about sorting:
- Give na sequence of elements with $Z$ inversions
- Performa a sequence of operations that reduces inversions to $0$.



