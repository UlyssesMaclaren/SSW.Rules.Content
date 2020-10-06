---
type: rule
title: Schema - Do you create primary key on your tables?
uri: schema---do-you-create-primary-key-on-your-tables
created: 2019-11-05T23:57:23.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

When you specify a PRIMARY KEY constraint for a table, SQL Server enforces data uniqueness by creating a unique index for the primary key columns. This index also permits fast access to data when the primary key is used in queries.
Although, strictly speaking, the primary key is not essential - we recommend all tables have a primary key (except tables that have a high volume of continuous transactions).

[[badExample]]
| ![Table missing primarykey](SqlTableWithoutPrimaryKey.PNG)

[[goodExample]]
| ![Table with primary key](SqlTableWithPrimaryKey.PNG)


**Legacy:**

Especially, when you have a client like Access, it would help you to avoid the problems.
