---
title: "Binomial Coefficient"
enableToc: true
date: 2023-01-11
tags:
- Stats-110
- Stats
---

$${n \choose k} = \dfrac{n!}{(n-k)!k!}$$


In english, you can think of this statement as saying 

>If we have $n$ people, how many ways can we choose $k$ people out of the $n$ people?

## Derivation 

**Definitions:** Number of subsets of size $k$, of group $n$ people, where order doesn't matter.


If we had $n$ people and wanna select $k$ of them, here's how we'd start.

Let's pick the first person. There are $n$ choices, so our expression looks like this:

$$ n $$

Let's pick the second person. There are $n-1$ choices left, since we already picked one.

$$ n (n -1) $$

Same thing for the third one

$$ n (n - 1) (n - 2) $$

This generalizes 

$$ n (n - 1) (n - 2) \cdots $$

We stop at $(n-k+1)$ because if $k = 1$, we want to stop at n. If $k = 2$, we want to stop at $n-1$, etc.

$$ n (n - 1) (n - 2) \cdots (n - k + 1) $$

This would be correct if we were picking people in a specific order. But in this case, we could've selected these people in any order. 

We have to divide by $k!$ because there are $k!$ ways to order the people. 

$$ \dfrac{n (n - 1) (n - 2) \cdots (n - k + 1)}{k!} $$

It turns out this is the same as

$$ \dfrac{n!}{(n-k)!k!} $$

Note that if $k > n$ then ${n \choose k} = 0$ because it wouldn't make sense to pick 11 people out of 10 people.





