---
title: "Red Black Trees Rules"
enableToc: false
date: 2022-12-30
tags:
- Data-Structures
- Software
---

# Red Black Tree Rules


When inserting: use a red link
- If there is a right leaning "3-node", we have a left leaning violation.
 - Rotate left 
- If there are two consecutive left links, we have an incorrect 4-node violation
    - Rotate right
- If a node has two red link children, we have a temporary 4-node violation
    - Flip colors


One last detail: Cascading operations
- It is possible that a rotation or flip will cause an additional violation that needs fixing.

