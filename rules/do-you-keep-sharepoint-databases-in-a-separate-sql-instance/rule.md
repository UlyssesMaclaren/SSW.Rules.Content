---
type: rule
archivedreason: 
title: Do you keep SharePoint databases in a separate SQL instance?
guid: 8b120644-476c-4b48-9bd0-acf1e37ff4aa
uri: do-you-keep-sharepoint-databases-in-a-separate-sql-instance
created: 2018-06-25T23:34:07.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 9
  title: William Yin
related: []
redirects: []

---

Because SharePoint server will create quite a few databases, it’s easier to manage them in a separate SQL instance rather than mixing it with other system’s databases:

<!--endintro-->

![example](sharepoint-database-bad.png)Bad
![example](sharepoint-database-good.png)Good
