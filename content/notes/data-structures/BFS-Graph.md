---
title: "BFS and Graph Algorithm Implementations"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---


So far, we have seen a few graph traversals;
- DFS Preorder: returns in order of dfs calls
- DFS Postorder: returns in order of dfs returns
- BFS order: returns in order of distance from source

BFS order is analogous to level order traversal.

## Typical BFS Implementation

The typical BFS implementation is non-recursive. 
- Initialize the fringe (A queue with a starting vertex $s$) and mark that vertex.
- Repeat until fringe is empty:
    - Mark vertex $v$ from fringe 
    - For each unmarked neighor $n$ of $v$: mark $n$, add $n$ to fringe, set `edgeTo[n]` to `v`, set `distTo[n] = distTo[v] + 1`.

The queue data structure is going to enforce the idea that we need to traverse in the order of distance from the source. 

An invariant of BFS is that distance to all items on queue is always $k$ or $k+1$ for some $k$. 

## Graph API 1: Integer Vertices

Common convention: Number nodes irrespective of "label", and use number throughout the graph implementation. `Map<Label, Integer>`.

## Graph API 2: Princeton Graph API

```
public class Graph {
    public Graph(int V);
    public void addEdge(int v, int w);
    Iterable<Integer> adj(int v);
    int V();
    int E();
...
```

- Number of vertices must be specified in advance.
- Does not support weights on nodes
- Has no method or getting the number of edges for a vertex (its degree);
 

## Graph Representations

### Adjacency Matrix

<!-- Draw an adjacency matrix for the graph in the previous slide. -->

|   | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|---|
| 0 |   |   |   |   |   |   |   |   |   |   |
| 1 |   |   |   |   |   |   |   |   |   |   |
| 2 |   |   |   |   |   |   |   |   |   |   |
| 3 |   |   |   |   |   |   |   |   |   |   |
| 4 |   |   |   |   |   |   |   |   |   |   |
| 5 |   |   |   |   |   |   |   |   |   |   |
| 6 |   |   |   |   |   |   |   |   |   |   |
| 7 |   |   |   |   |   |   |   |   |   |   |
| 8 |   |   |   |   |   |   |   |   |   |   |
| 9 |   |   |   |   |   |   |   |   |   |   |

Takes $O(V^2)$ time complexity.

### Adjacency List

Maintain an array of lists indexed by vertex. This is the most popular representation. This is because graphs are often sparse (not many edges in each bucket).

- Most graph algorithms rely heavily on `adj(s)`.


 
