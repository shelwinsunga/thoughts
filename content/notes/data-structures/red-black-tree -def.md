---
title: "Red Black Trees Definition"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---


 Red Black Trees are trees that are structurally indentical to B-Trees, but have glue links. This idea is commonly used in practice  (ex: `java.util.TreeSet`).

 A BST with left glue links are called a **left-leaning red-black BST**. 
 - LLRBs are normal BSTs.
 - There is a 1-1 correspondence between an LLRB and an equivalent 2-3 tree. 
 - The red is just convenient fiction. Red links don't "do" anyything special.

# Red Black Tree Properties

From this, we get two very important properties:
- No node has two red links connected to it.
- Every path from a leaf node to the root has the same number of black links.

Therefore, LLRBs are **perfectly balanced**.

The way we'd implement this is to insert as usual into a BST, and then do some number of rotations to maintain the 1-1 mapping. 


