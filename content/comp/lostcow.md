---
title: "The Lost Cow"
enableToc: false
date: 2022-11-09
tags:
- USACO
- Bronze
- CP
---


USACO 2017 US Open Contest, Bronze - Problem 1. The Lost Cow
# Problem Statement

Farmer John has lost his prize cow Bessie, and he needs to find her!
Fortunately, there is only one long path running across the farm, and Farmer John knows that Bessie has to be at some location on this path. If we think of the path as a number line, then Farmer John is currently at position $x$ and Bessie is currently at position $y$ (unknown to Farmer John). If Farmer John only knew where Bessie was located, he could walk directly to her, traveling a distance of $|x−y|$. Unfortunately, it is dark outside and Farmer John can't see anything. The only way he can find Bessie is to walk back and forth until he eventually reaches her position.

Trying to figure out the best strategy for walking back and forth in his search, Farmer John consults the computer science research literature and is somewhat amused to find that this exact problem has not only been studied by computer scientists in the past, but that it is actually called the "Lost Cow Problem" (this is actually true!).

The recommended solution for Farmer John to find Bessie is to move to position $x+1$, then reverse direction and move to position $x−2$, then to position $x+4$, and so on, in a "zig zag" pattern, each step moving twice as far from his initial starting position as before. As he has read during his study of algorithms for solving the lost cow problem, this approach guarantees that he will at worst travel 9 times the direct distance $|x−y|$ between himself and Bessie before he finds her (this is also true, and the factor of 9 is actually the smallest such worst case guarantee any strategy can achieve).

Farmer John is curious to verify this result. Given $x$ and $y$, please compute the total distance he will travel according to the zig-zag search strategy above until he finds Bessie.

#### Input Format (cowsignal.in)

The single line of input contains two distinct space-separated integers $x$ and $y$. Both are in the range $0 \ldots 1,000$.

#### Output Format (cowsignal.out)

Print one line of output, containing the distance Farmer John will travel to reach Bessie.



#### Sample Input: 
3 6
#### Sample Output:

9

# My Solution
<br>

```
#include <iostream>
#include <vector>
using namespace std;

int main() {
  freopen("lostcow.in", "r", stdin);
  freopen("lostcow.out", "w", stdout);

  int x, y;
  scanf("%d %d", &x, &y);
  int origin = x;

  int d = 0;
  int k = 1;

  // approach:
  int turn = 1;
  while (x != y) {
    if (turn % 2 != 0) {
      for (int i = 1; i <= k; i++) {
        if (x == y)
          break;
        x++;
        d++;
      }

      for (int i = 1; i <= k; i++) {
        if (x == y)
          break;
        x--;
        d++;
      }

    } else {
      for (int i = 1; i <= k; i++) {
        if (x == y)
          break;
        x--;
        d++;
      }

      for (int i = 1; i <= k; i++) {
        if (x == y)
          break;
        x++;
        d++;
      }
    }
    k *= 2;
    turn++;
  }

  cout << d << endl;
  return 0;
}

```
