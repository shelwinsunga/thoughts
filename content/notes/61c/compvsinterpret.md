---
title: "Compiler vs Interpreters"
enableToc: false
date: 2023-03-24
tags:
  - 61C
---

See also: [Number Representation](numbers.md)

C works in compilation. It takes a program, and turns it into architecture-specific machine code (a string of 1's and 0's). Architecture-specific because companies like Apple and Intel have their own machine code.

This is unlike Java, which converts to architecture-independent bytecode that may then be compield by a just-in-time compiler. Java has both a compiler and interpreter.

Python does a realtime bytecode compilation. It compiles to bytecode as it runs.

These differ mainly in exactly when your prrogram is converted to machine code.

## Compilation

### Advantages

Compiled languages in general are as fast as it gets. It basically runs on raw silicon.

But then why do we do scientific computation in Python?

- Good libraries for accessing GPU-specific resources.
- Also, many times python allows the ability to drive many other machines very easily.
- Also, Python can call low-level C code: Cython

### Disadvantages

The "Change -> Compile -> Run" cycle is slow.

Also, we have to compile for each architecture we want to run on. This movement is called "portability", and is always a pain.

- If you type `make -j` you can compile in parallel, which is quite fast. Linking, however, is still slow (the bottleneck) because of Amdahl's Law.
