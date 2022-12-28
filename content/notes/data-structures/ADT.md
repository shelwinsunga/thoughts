---
title: "Abstract Data Types"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

Abstract Data types are defined by their operations, not their implementation.

# The Stack ADT
The Stack ADT supports the following operations:
- `push(x)`: Add an element to the top of the stack.
- int pop(): Remove the top element from the stack and return it.

A linked list and array implementation are basically equally efficient.

# GrabBag ADT
- `add(x)`: Add an element to the grab bag.
- int `remove()`: Remove a random element from the grab bag and return it.
- int `sample()`: Return a random element from the grab bag.
- int `size()`: Return the number of elements in the grab bag.

Arrays turn out to be a better implementation than linked lists.

    
