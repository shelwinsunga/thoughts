---
title: "Graphs"
enableToc: false
date: 2022-12-31
tags:
- Data-Structures
- Software
---

Trees are fantastic for representing strict hierarchial relationships.
- But not every relationship is hierarchial.

A graph consists of:
- a set of nodes
- a set of zero or mor edges, which connects two nodes.

# Simple Graphs

A simple graph is a graph with:
- no edges that connects a vertex to itself, i.e. no loops
- No two edges that connect the same vertices, i.e. no parallel edges.
  
Note you can think think of edges as a pair of vertices.

Vertices with an edge between are called adjacent.

Vertices or edges may have **labels** or **weights**.

A **path** is a sequence of vertices such that each pair of consecutive vertices is connected by an edge.

A cycle is a path that starts and ends at the same vertex.
  
A graph with a cycle is called **cyclic**. A graph without a cycle is called **acyclic**.

Two vertices are **connected** if there is a path between them. If all vertices are connected, the graph is connected.

There is other terminology, like vertex degree and connected components.


  