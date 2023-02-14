---
title: "Number Representation"
enableToc: true
date: 2023-01-28
tags:
- 61C
---

The real world is composed of analog data. As computer scientists, we want to turn that into digital data so we can do things with it.

To convert, we have to sample and quantize. An example of sampling is asking every 44,100th of a second how loud a music signal is on a CD. An example of quantization is asking how loud the music is in 256 different levels.

# Big Idea: Bits can represent anything!

- Characters
- ASCII and Unicode
- Logical Values
- Colors
- Locations
- Addresses
- Commands
- Emotions

Typically when we say something is $N$ bits, we mean it's $2^N$ different values.

# Base 10

We use base 10 because we have 10 fingers. In base 10, we have 10 digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9. We can use these digits to represent any number. For example, 1234 as $1 \times 10^3 + 2 \times 10^2 + 3 \times 10^1 + 4 \times 10^0$.

##  Base 2

In base 2, we have 2 digits: 0 and 1. We can use these digits to represent any number. We denote we're using binary by putting a `0b` in front of the number. So `0b1010` is 10.

For example, 1010 as $1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 0 \times 2^0$.

## Base 16

This is called Hexadecimal. We have 16 digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F. We can use these digits to represent any number. 

We denote we're using hexadecimal by putting a `0x` in front of the number. So `0x10` is 16.

`0xA5` is $10 \times 16^1 + 5 \times 16^0 = 160 + 5 = 165$. Note that A, B, C, D, E, F are 10, 11, 12, 13, 14, 15 in base 10.

# Convert from Binary to Hex

Always left pad with 0s to make it a multiple of 4. Then convert 4 bits at a time using the table below.

| Binary | Hex |
|--------|-----|
| 0000   | 0   |
| 0001   | 1   |
| 0010   | 2   |
| 0011   | 3   |
| 0100   | 4   |
| 0101   | 5   |
| 0110   | 6   |
| 0111   | 7   |
| 1000   | 8   |
| 1001   | 9   |
| 1010   | A   |
| 1011   | B   |
| 1100   | C   |
| 1101   | D   |
| 1110   | E   |
| 1111   | F   |

For example, `0b1010` is `0xA`. `0b11110` needs to be left padded with 0s to make it a multiple of 4. So it's now `0b00011110`. Then we convert 4 bits at a time. So `0b0001` is `0x1` and `0b1110` is `0xE`. So `0b11110` is `0x1E`.

## Hex to Binary

From Hex to Binary is the same process, but in reverse. Just drop leading 0s.


# Decimal vs Hex vs Binary

4 bits is called a nibble. 8 bits is called a byte.

1 hex digit is 16 things. 2 hex digits is 256 things. 

Color is usually 0-255 red, 0-255 green, 0-255 blue. This means it's 6 hex digits. 

# Which base do we use?

Decimal: Humans
Hex: If human is looking at long strips of binary numbers, it's easier to read hex. 
Binary: Computers will use binary.   


