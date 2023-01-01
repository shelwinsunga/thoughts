---
title: "Tree Traversals"
enableToc: true
date: 2022-12-31
tags:
- Data-Structures
- Software
---

Unlike a linked list, where you can traverse the list by following the `next` pointers, a tree is a bit more complicated. There are more ways to traverse a tree.

## Level Order Traversal
- Visit top-down, left to right (like reading in English)

## Depth First Traversals

There are three types of depth first traversals:
- Preorder
- Inorder
- Postorder

The basic idea is to traverse "deep nodes" before shallow ones. Note that traversing a node is different than "visiting" a node. 

## Preorder

A PreOrder traversal is a depth first traversal where the root is visited first, then the left subtree, then the right subtree. 
  
``` 
preOrder(BSTNode x){
    if(x == null) return;
    print(x.key);
    preOrder(x.left);
    preOrder(x.right);
}
```

## Inorder

A InOrder traversal is a depth first traversal where the left subtree is visited first, then the root, then the right subtree. 

```
inOrder(BSTNode x){
    if(x == null) return;
    inOrder(x.left);
    print(x.key);
    inOrder(x.right);
}
```

## Postorder

A PostOrder traversal is a depth first traversal where the left subtree is visited first, then the right subtree, then the root. 

```
postOrder(BSTNode x){
    if(x == null) return;
    postOrder(x.left);
    postOrder(x.right);
    print(x.key);
}
```

# Handy Trick

To visualize a traversal, you can do the following:

Trace a path around the graph, from top going counter-clickwise.
- Preorder: Visit node everytime we pass the left of a node
- Inorder: Visit node everytime we pass the bottom of a node
- Postorder: Visit node everytime we pass the right of a node