---
type: rule
title: Schema - Do you create clustered index on your tables?
uri: schema---do-you-create-clustered-index-on-your-tables
created: 2019-11-06T00:30:09.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

You're allowed one clustered index per table, so unless you are never going to query a table, you may as well choose a field to be part of a clustered index. Basically,

1. Every table should have a clustered index;
2. The clustered index should be a unique clustered index where possible;
3. The clustered index should be on a single column where possible;

 
So how do you choose the right field? Depending on the usage pattern of a table, clustered indices should be created. If sets of related records are regularly retrieved from a table in an application, a clustered index could dramatically improve performance.

For example, in an Order to OrderDetails relationship with OrderID as the joining key, items in an order are regularly retrieved in a bundle. A clustered index on the OrderID column in the OrderDetails table will improve the performance of the application significantly.

Another example, if a table is frequently used for reporting, and a date range is used to define the time scope of the report, a clustered index on the date column is suitable. In more technical terms, if queries such as...

SELECT \* FROM ReportTable WHERE ItemDate BETWEEN 1/1/2003 AND 1/2/2003

...is executed frequently, ItemDate is a good candidate column for a clustered index.
