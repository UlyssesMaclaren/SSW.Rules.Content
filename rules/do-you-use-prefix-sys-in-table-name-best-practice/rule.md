---
type: rule
title: Do you use prefix sys in table name (Best Practice)?
uri: do-you-use-prefix-sys-in-table-name-best-practice
created: 2010-07-23T02:47:37.0000000Z
authors:
- id: 1
  title: Adam Cogan

---


Don't use sys as a prefix for Access tables. Some developers use this for system tables etc. SQL Server uses tables with this prefix and it becomes confusing. We recommend system tables start with **zs** eg. zsUsers




| [Upsizing PRO](http&#58;//www.ssw.com.au/ssw/UpsizingPRO) will check this rule  |
| --- |

 See our [Rules to Better SQL Server Databases - Do you add zs prefix to table name?](http&#58;//www.ssw.com.au/ssw/Standards/Rules/RulesToBetterSQLServerDatabases.aspx#ZSPrefix)
