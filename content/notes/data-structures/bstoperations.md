---
title: "BST Operations"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

# Search

If searchKey = T.key, return.
- If searchKey < T.key, search T.left;
- If searchKey > T.key, search T.right;

Runtime to complete search on a bushy BST in the worst case is $O(log(n))$. This is intuitive to see and you can generally estimate the number of computations needed to search a BST by the height of the tree.

Remember, the height of the tree is roughly $log(n)$. So if the tree is 15 nodes, $log(15) = 4$. So the worst case runtime is $O(4) = O(1)$.

Bushy BSTs are extremely fast.

At 1 microsecond per operation, can find something from a tree with $10^{300000}$ nodes in one second. 

Much (perhaps most?) computation is dedicated towards finding things in response to queries. 

# Insert 

Search for key. 
- If found, do nothing.
- If not found 
  - Create a new node
  - Set appropiate link. 

# Delete

3 cases: 

- Deletion key has no children
- Deletion key has one child
- Deletion key has two children


In the first case, we just sever the link. It gets collected by the garbage collector.
In the second case, we replace the node with its child. Note that even though the deletion key might still be pointing to the child, it will still get collected by the garbage collector.
In the third case, we replace the node with its predecessor or the successor. Note that the predecessor or successor are guarenteed to have at most one child.

This is usually known as Hibbard deletion.

# BSTs as Sets and Maps


The BST we created could be thought of as a set. But we can also use it as a map. This is done by storing each BST node as key/value pairs. Note that there is no efficient way to look up a value in a BST.
- Example: Cannot find all the keys with value = 1 without iterating over ALL nodes. This is fine. 

