---
title: "Graph Problems"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---

# Graph Queries

There are a lot of interesting questions we can ask about a graph. What is the shortest path between two points? Are there cycles? What is the longest path without cycles?

Is there a path we can take that only uses each node exactly once? Is there a tour that uses each edge exactly once?

What's interesting about these problems is that they're solved with traversals.

# Well known Graph Problems

- **s-t path problem**: Given a graph and two vertices s and t, is there a path from s to t? (GPS)
- **Connectivity**: Is the graph connected? I.e. is there a path between all vertices? (A generalization of the s-t path problem)
- **Bi-connectivity**: Is there a vertex whose removal would disconnect the graph? (Biconnectivity might be a bad because you'd have a single point of failure)
- **Shortest s-t path**: Given a graph and two vertices s and t, what is the shortest path from s to t? (Google Maps)
- **Cycle detection**: Is there a cycle in the graph?
- **Euler Tour**: Is there a cycle that uses each edge exactly once?
- **Hamiltonian Tour**: Is there a cycle that uses each vertex exactly once?
- **Planarity**: Can you draw the graph on paper with no crossing edges?
- **Isomorphism**: Are two graphs the same? 

We often can't tell how difficult a graph problem is without very deep consideration. 

An efficient Euler tour algorithm O(# edges) was found as early as 1873. But despite decades of intense study, no efficient algorithm for a Hamilton tour exists. Best algorithms are exponential time.

Graph problems are among the most mathemtically rich areas of CS theory.



