---
title: "Relational Model"
enableToc: false
date: 2022-11-0
tags:
- CMU 15-445/645
- Software
- Coursework
---

Let's say we were building an application that models a digital music store to keep track of artists and albums. Meaning, we'd need to store two things:

- Information about Artists
- What albums those artists have released



# Flat File Strawman

The most basic approach we can take is creating a two CSV files (artists.csv and albums.csv), and then parsing the files with elementary code anytime we want to read or update the records. 

# Flat files: Data Integrity

