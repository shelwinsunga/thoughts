---
title: "Advanced SQL"
enableToc: false
date: 2023-02-14
tags:
  - Databases
  - Software
---

See Also: [Introduction to Databases](introdb.md)

## A Brief History of SQL

**SQL**, or Structured English Query Language, was originally released as 'SEQUEL' from IBM's System R prototype. It was later adopted by Oracle in the 1970s. IBM was the great big tech juggernaut - what today we'd look at Google and Facebook as - and so anything they did, the entire techno world followed. IBM later released DB2.

Even though SQL is an old language (made in the 70s), that doesn't mean it's a dead language. It is still updated and improved upon.

- In 2016, they added JSON, and Polymorphic tables.
- In 2011, they added Temporal DBs, and piplined DML.
- In 2008, they added TRUNCATE, and Fancy ORDER
- In 2003, they added XML, windows, sequences, auto-generated IDs.
- In 1999, they added Regex, triggers, OO

The way standards are developed, like the SQL standard, is by numerous companies submitting proposals to the standards committee. The committee then votes on the proposals, and the ones that get the most votes are added to the standard. Despite there being standards, no one follows it to the T. Most DBMSs at least support SQL-92, which contains the primitives of SQL as we know it.

## Relational Languages

SQL is a collection of different things. Data Manipulation Language (DML), which defines how to manipulate data through commands like `SELECT`, `INSERT`, `UPDATE`, and `DELETE`. Data Definition Language (DDL), which defines how to define the structure of the database through commands like `CREATE`, `ALTER`, and `DROP`. Data Control Language (DCL), which defines how to control the access to the database through commands like `GRANT`, `REVOKE`, and `DENY`. There are other things like view definitions, integrity and referential constraints, and transactions.

Importantly, unlike Relational Algebra which is based on Set Theory, SQL is based on Bags. Recall lists and sets. In a list, you can have duplicates, and there is a sense of order (I can tell you what position something is in). In a set, things are unordered but you can't have duplicates. A bag is unordered and can contain duplicates.

## Aggregates

Aggregations are a way to summarize data. They are functions that return a single value from a bag of tuples. In the SQL-92 standard, there are 5 aggregates: `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX`. Overtime, aggregates like `STDDEV` and `VARIANCE` have been added.

_Get # of students with a "@cs" login:_

```sql
    SELECT COUNT(1) FROM students WHERE email LIKE '%@cs%';
```

There also DISTINCT aggregates, in which we only get unique values.

## String Operations

Different SQL standards will be case sensitive or case insensitive, and will have single quotes or double quotes. Most are case sensitive, and use single quotes.
