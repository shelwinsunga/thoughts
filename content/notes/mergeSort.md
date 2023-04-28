---
title: "Merge Sort"
enableToc: false
date: 2023-04-28
tags:
  - Software
---

# Merge Sort

You probably know about naive sorting methods: selection sort, insertion sort, bubble sort, etc. These are all $O(n^2)$ algorithms, which is quite bad.

Merge sort is a much more efficient algorithm, and we'll walk through its implementation and it's analysis.

## Algorithm

MergeSort is a valuable exercise for teaching divide and conquer programming. Here's the steps:

```
Input: A[1..n] of orderable elements
Output: A[1..n] in sorted order

if n = 1, return
else
  recursively sort A[1..n/2]
  recursively sort A[n/2+1..n]
  merge the two sorted subsequences
```

Basically, we split the array in half, recursively sort each half, and then merge the two sorted halves.

We need a merging function as a subroutine. Here's the pseudocode:

```
Input: C[1..p], D[1..q] are sorted
Output: B[1..p+q] is sorted

i = 1
j = 1
for k = 1 to p+q
  if C[i] < D[j]
    B[k] = C[i]
    i++
  else
    B[k] = D[j]
    j++

return B
```

## Analysis

Let's rigorously analyze this algorithm. First, let's try and understand the running time of `merge`.

We have 2 initializations, so that's two operations in this function. we can see that the loop runs $p+q$ times. We'll call this $l$.

Next, we have two comparisons, an assignment, and an increment. This adds up to 4 times. So far we have $4l + 2$.

Our upper bound will be $6l$.

Every recursive call is passed an input substantially smaller than the one we started with. There's a tension between two competing forces: on the one hand, the explosion of different subproblems that need to be solved; on the other, the ever-shrinking inputs for which these subproblems are responsible. We end up with a runtime of:

<!-- 6nlogbase2n + 6n -->

$$ 6n\log_2n + 6n $$

Which means our worst case runtime is $O(n\log n)$.
