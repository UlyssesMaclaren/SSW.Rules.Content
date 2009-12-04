---
type: rule
title: Do you know when to use CAML instead of object model?
uri: do-you-know-when-to-use-caml-instead-of-object-model
created: 2009-04-09T06:10:00.0000000Z
authors:
- id: 8
  title: John Liu
- id: 18
  title: Jay Lin

---

 This field should not be null (Remove me when you edit this field). 
The SharePoint object model is very comprehensive and lets you select items from lists, select lists from sites, in site-collections within web-applications.

Naturally, using the object model is great for traversing all elements in a list.  Once you have a handle to the item, you can also easily modify that item.

On the other hand, one of the SharePoint class SPSiteDataQuery allows a developer to use CAML to specify a query condition that SharePoint can understand to search and return matching elements from across the entire site collection.

This is the underlying class that the Content Query Web Part relies on.

So, you need to use object model when you want to:

- Iterate all elements in a list
- Modify elements in a list


And you use CAML, whether in CQWP or in code with SPSiteDataQuery to:

- Select, filter elements from SharePoint lists
- Select elements from multiple lists


