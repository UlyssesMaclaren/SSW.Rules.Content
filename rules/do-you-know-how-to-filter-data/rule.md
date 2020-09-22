---
type: rule
title: Do you know how to filter data?
uri: do-you-know-how-to-filter-data
created: 2009-08-24T04:04:26.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 It is difficult for users to find their required records in a huge amount of data, so adding the filter data functionalities is very useful.  <br> 
The standard DataGrid of ASP.NET doesn't include this functionality, developers need to implement it by themselves.
![Bad Example - implement data filter manually](FilterDataInDataGrid.jpg) Figure: Bad Example - implement data filter manually
Fortunately, RadGrid supplies this perfect feature.
![Good Example - add an attribute to filter data](FilterDataInRadGrid.jpg) Figure: Good Example - add an attribute to filter data
Developer can turn this feature on by setting the AllowFilteringByColumn="True".

