---
title: "Hashing Intro"
enableToc: false
date: 2022-12-27
tags:
- Data-Structures
- Software
---

Our search trees have excellent $O(log(n))$ performance. Can we do better? And can we do it without comparisons?

# Approach: Taking advantage of arrays

The idea is simple: Create a boolean array of $N$ length that is initialized as false. Whenever we add an element, we set the corresponding index to true. 

This makes `contains` and `add` O(1).

The draw back is that we use a ridiculous amount of memory, and we don't yet have a way to generalize data types. 

# ASCII and Unicode

The ASCII Standard is the most basic character set used by computers. It is a 7-bit character set, which means it can represent 128 different characters.

If we want to represent more characters, we can use Unicode. Unicode is a 16-bit character set, which means it can represent 65,536 different characters. This would include things like Chinese characters, emojis, and other symbols.

We can use the ASCII and Unicode character sets to create a hash function.

# Integer Overflow

In Java, the largest possible Integer is 2,147,483,647. If we add 1 to this number, we get -2,147,483,648. This is called integer overflow, meaning we start back at the smallest possible integer.

This means that if we represent words in ASCII, which is base 128, we can only represent 2,147,483,647 words. Which means we can get collisions. 

THe term we use is 'hash code' to refer to the integer that we get from our hash function. Wolfram Alpha says that a hash code "projects a value from a set with many (or even infinite) members to a value from a set with a fixed (fewer) number of members."

The pigeonhole principle tells that we will get collisions. It is inevitable.

That leaves us with two fundamental challenges:

1. How do we avoid collisions?
2. How do we compute the hash code for arbitrary objects?

