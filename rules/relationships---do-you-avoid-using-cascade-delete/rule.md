---
type: rule
title: Relationships - Do you avoid using Cascade Delete?
uri: relationships---do-you-avoid-using-cascade-delete
created: 2019-11-13T00:23:04.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

SQL Servers ON DELETE CASCADE functionality can be very dangerous. We recommend not using it. Imagine someone deletes customer and the orders are deleted. If you need to delete records in related tables, do it in code in the application as it gives you more control.
