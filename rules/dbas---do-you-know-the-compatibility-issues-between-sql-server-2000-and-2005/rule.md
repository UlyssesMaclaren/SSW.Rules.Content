---
type: rule
title: DBAs - Do you know the compatibility issues between SQL Server 2000 and 2005?
uri: dbas---do-you-know-the-compatibility-issues-between-sql-server-2000-and-2005
created: 2019-11-22T21:30:50.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

The SQL 2005 generated scripts are not compatible with​ SQL 2000, so use SQL 2000 to generate your scripts if you want to make your scripts work well on both versions.​​
 
IF EXISTS (SELECT \* FROM sys.objects WHERE object\_id = OBJECT\_ID(N'[dbo].[ProcessTarget]') AND type in (N'P', N'PC'))
drop procedure [dbo].[ProcessTarget]
Figure: script only works on SQL 2005, because 'sys.objects' is only available in this version

IF EXISTS (SELECT \* FROM dbo.sysobjects WHERE id = OBJECT\_ID(N'[dbo].[ProcessTarget]') AND OBJECTPROPERTY(id, N'IsProcedure') = 1)
drop procedure [dbo].[ProcessTarget]
Figure: script works on both SQL 2000 and SQL 2005​
