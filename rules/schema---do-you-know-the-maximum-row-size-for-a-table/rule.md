---
type: rule
title: Schema - Do you know the maximum row size for a table?
uri: schema---do-you-know-the-maximum-row-size-for-a-table
created: 2019-11-05T23:20:11.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
​A​ tables' maximum row size should be less than the size of a single SQL Server data page (8060 bytes). Otherwise, data entry forms can give errors is not validated correctly.
 
