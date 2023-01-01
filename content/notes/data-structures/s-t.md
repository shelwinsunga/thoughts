---
title: "S-T Connectivity"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
- Graphs
---

See Also: [Graph Problems](graph-problems.md)

Let's solve a classic graph problem called s-t connectivity problem.
- Given source vertex $s$ and a target vertex $t$, is there a path from $s$ to $t$?

# Recursive Solution

One possible recursive solution goes as follows:
- Mark $s$
- Does `s == t`? If so, return true.
- Else, `if connected(v,t)` for any unmarked neighbor $v$ of $s$, return true.
- Return false.

Each vertex is visited at most once.
- Marking nodes prevents multiple visits (infinite loops).

# Depth First Traversal

The idea of exploring a neighbor's entire subgraph before moving on to the next neighbor is known as Depth First Traversal.

## Depth First Paths 

Find a path from $s$ to every reachable vertex, visiting each vertex at most once. `dfs(v)` is as follows:

- mark `v`
- For each unmarked adjacent vertex `w`
  - set `edgeTo[w]` to `v`
  - `dfs(w)`



