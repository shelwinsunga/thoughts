---
title: "Git"
enableToc: false
date: 2022-11-0
tags:
- CMU 15-445/645
- Software
- Coursework
---


Git is a version control system tool that has a CLI.

- Written in C
- Compiled into a binary which doesn't require an interpreter

# Git: How it works

Everytime you commit changes to a fil, it stores a copy of the entire repository in a secret folder on your computer called `.git`.

We store all the "versions" of our repository in the git directory with a hash. Specifically, the `git-SHA1` hash (SHA means Secure Hash Algorithm). 

The `git-SHA1` hash is a deterministic (non-random) function of the file's contents.
- Two identifical files will always have the same `git-SHA1`` hash.
- `git-SHA1` hash is 160 bits long represented as a hexadecimal.

You can compute the hash with the `hash-object` directive. Example: `git hash-object hello.js`

# Using the `git-SHA51` hash

If we wanted to store `hello.txt`, we'd first compute it's hash. 
- `hello.txt` --> `aae6c35c94fcfb415dbe95f408b9ce91ee846ed`

Git creates a folder called `.git/objects/aa` because the hash begins with `aa`. 

Git stores the contents in a file called `e6c35c94fcfb415dbe95f408b9ce91ee846ed`. This file is stored in a compressed format (zlib) to save space.

Okay - but theoretically two files could have the same SHA hash right? There are an infinite number of different files we could create and a finite number of hashes (160 bits).

The good news is that the chance that two files have the same SHA hash is $\dfrac{1}{2^{160}}$ or roughly $\dfrac{1}{10^{27}}$.
- We would need roughly $2^{80}$ before we expect to see two files with the same `SHA` hash.

In other words, git has a bug. But it is unlikely to ever occur in the history of the universe. 

## Security

We also are able to use the hash to verify file integrity. If someone wanted to sneak malicious code into our `objects/{hash}` file and replace it, it would change the hash value and let git know.

# Commit

Every git commit stores
- An author
- A date
- A commit message
- A list of all files and their versions
    - Versions are `git-SHA1` hashes
- The parent's commit ID
 
So you can imagine a commit as some kind of file that has all of that meta data and then becoming hashed. 

# Branching







