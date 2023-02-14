---
title: "Introduction to Databases"
enableToc: false
date: 2023-02-14
tags:
  - Databases
  - Software
---

The simplest database we can have is a bunch of CSV files that we can manage with our own code. For every entity, we'll store them in our own file (album.csv, artists.csv). The application will parse / read / write.

There are a lot of issues with this approach:

- Data Integrity
  - invalid strings, typos, etc
- Implementation
  - Slow
  - What if we want to create a new application with the same database?
  - What if two threads try to write to the same file at the same time.
- Durability
  - What if the machine crashes while our program is updating a record?
  - What if we want to replicate the database on multiple machines for high availability?

For these problems and others, we want to offload that complex logic. We use a **Database Management System** (DBMS). We can define, create, query, update, administer databases (we assume DB's are on disk).

Early DBMs were hard to build and maintain. Tight coupling between logical and physical layers. You have to know what queries your app would execute before you deployed the database.

Edgar Codd proposed the relational model. The first paper came out on 1969 and the one that most people read was in 1970. He proposed:

- Store database in simple data structures (the idea of a relation isn't like being related to your parents - it's synonymous with tables)
- Access data data through high-level languages (back then, we were writing explicit produral code to interact with the database)
- Physical storage left up to implementation (How things are stored aren't a part of the relational model - this allowed flexibility when it came to change how things are stored, which would often depend on how an application might scale overtime)

There are other data models, which are ways we can describe the data in a database.

At the top we have the relational model. Than we have NoSQL, which are key/value, document/json, graph models, column/family. Array / Matrix databases are used in machine learning, we mostly use dataframes. There are hierachical and Network datamodels but are esoteric, obsolete/rare, and are seen in legacy applications. They are remnants of old software, don't use them.

## Relational Model

There are three components of the relational model:

- Structure: The definition of relations and their contents
- Integirty: Ensure the database's contents satisfy constraints.
- Manipulation: How to access and modify a database's contents.

A relation is an unordered set that contains the relationship of attributes that represent entities (ARtist(name, year, country).

A **tuple** is a set of attribute values (also known as its domain) in the relation.

- Values are (normally) atomic/scalar (this particular constraint was placed by Codd in the 70s, but is now relaxed. We can have array/json objects as values in modern DBMSs).
- The special value `NULL` is a member of every domain.

An `n-ary` relation means a Table with $n$ columns.

A relation's **primary key** uniquely identifies a single tuple. Some DBMSs automatically create an internal primary key if you don't define one. Auto-generation of a unique integer primary keys:

- Sequence(SQL: 2003)
- Auto_Increment (MySQL)

A foreign key specifies that an attribute from one relation has to map to a tuple in another relation.

## Data Manipulation Languages (DML)

How do we store and retrieve information from a database?

- Procedural (Relational Algebra)

  - The query specifies the (high-level) strategy the DBMS should use to find the desired result.

- Non-Procedural (Relational Calculus)
  - The query specifies only what data is wanted and not how to find it.

## Relational Algebra

Edgar Codd proposed 7 fundamental operators in relational algebra to retrieve and manipulate tuples in a relation.

- Select, Projection, Union, Intersection, Difference, Product, Join

Each operator takes one or more relations as its inputs and outputs a new relation.

- We can "chain" operators together to create more complex operations.

### Select

The `SELECT` operator chooses a subset of the tuples from a relation that satisfies a selection predictate

- The predictate acts as a filter to retain only tuples that fulfill its qualifying requirement
- Can combine multiple predicates using conjunctions / disjunctions.

The syntax: $ \sigma_{\textnormal{predictate}}(R). $

In SQL this would be:

```sql
SELECT * FROM R WHERE a_id = 'a2' OR b_id = '103';
```

### Projection

Generate a relation with tuples that contains only the specified attributes.

- Can rearrange attributes ordering
- Can manipulate the values

Syntax: $ \Pi_{\textnormal{attributes}}(R) $

In SQL this would be:

```sql
SELECT b_id-100, aid FROM R WHERE a_id = 'a2';
```

### Union

Generate a relation that contains all tuples that appear in either only one or both input relations.

Syntax: $ R \cup S $

In SQL this would be:

```sql
SELECT * FROM R
UNION ALL
SELECT * FROM S;
```

### Intersection

Generate a relation that contains all tuples that appear in both input relations.

Syntax: $ R \cap S $

In SQL this would be:

```sql
SELECT * FROM R
INTERSECT
SELECT * FROM S;
```

### Difference

Generate a relation that contains all tuples that appear in the first relation but not the second.

Syntax: $ R - S $

In SQL this would be:

```sql
SELECT * FROM R
EXCEPT
SELECT * FROM S;
```

### Product

Generate a relation that contains all possible combinations of tuples from the input relation (cross product, cartesian product).

Syntax: $ R \times S $

This might sound stupid but it's useful for something like testing where you want to test every possible combination of inputs / configurations.

### Join

Generate a relation that contains all tuples that are a combination of two tuples (one from each input relation) with a common value for one or more atttributes.

Syntax: $ R \bowtie S $

In SQL this would be:

```sql
 SELECT * FROM R NATURAL JOIN S;
```

## More operators

There are additional operators that people have added to the relational algebra.

- Rename ($ \rho $)
- Assignment ($ R \leftarrow S $)
- Duplicate Elimination ($ \delta $)
- Aggregation ($ \gamma $)
- Sorting ($ \tau $)
- Division ($ R / S $)

## Observation

Relational algebra still defines the high-level steps of how to compute a query. But this can still be inefficient because even though two queries might yield the same result, the performance of the two queries might be different because of the implementation details.

A better approach is to state the high-level answer that you want the DBMS to compute.

- Retrieve the joined tuples from $ R $ and $ S $ where `b_id = 102`.

The relational model is indepnende ot any query language implementation.

## Conclusions

Databases are ubiquitous.

Relational algebra defines the primitives for processing queries on a relational database.

We will see relational algebra again when we talk about query optimization + execution.
