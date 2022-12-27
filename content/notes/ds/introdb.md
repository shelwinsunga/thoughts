---
title: "Introduction to Databases"
enableToc: false
date: 2022-11-21
tags:
- Databases
- Software
---

In a very long sentence, Database Management Systems (DBMS) provides efficient, reliable, convenient, and safe multi-user storage of and access to massive amounts of persistent data.

# Massive

Database systems are handling terabytes of data and more. This is a lot of data, and it's growing every day. This is much more data than a single computer can handle. 

# Persistent

Data is typically persistent, meaning that the data in the database outlives the programs that execute on that data. By contrast, data in a program is typically volatile, meaning that the data in the program is lost when the program terminates.

# Safety

Database systems, since they provide critical applications like banking and telecommunication, must be safe. There has to be a guarentee that the data in the system won't be lost. There can be hardware failiures, software failiures, power outages, malicious users, etc. So there have to be mechanisms to ensure that the data is safe.

# Multi-user

Database systems are used by multiple users at the same time. This means that the database system has to provide concurrency control, which is the idea that multiple users can access the database at the same time without corrupting the data. We also don't want a single user having exclusive access to the database, because that would be cause performance to slow down considerably. 

# Convenient

Database systems are designed to be easy to work with large amounts of data, and do powerful and interesting things with that data. There are a couple levels of which that happens:

- Physical data independence - the physical storage of the data is hidden from the user. The user doesn't have to worry about how the data is stored, they just have to worry about how to access the data.

- High-level query languages (declarative) - the user doesn't have to worry about how to access the data, they just have to worry about what data they want.

- Effiency - databases have to do thousands of queries/updates per second. This means that the design of databases is not easy, and there are a lot of optimizations that go into making databases fast.

- Reliable - 99.9999% uptime is the goal. This means that the database has to be able to recover from hardware/software failures, and it has to be able to recover from user errors.




 