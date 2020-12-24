---
type: rule
archivedreason: 
title: DBAs - Do you turn on security auditing?
guid: fce19814-14c1-4032-9140-4127b0d39727
uri: dbas-do-you-turn-on-security-auditing
created: 2019-11-21T17:55:00.0000000Z
authors:
- id: 1
  title: Adam Cogan
related: []
redirects: []

---

Configure login security auditing:

* Not on by default
* Configure on the security tab of Server Properties in SQL Server Management Studio
* Enable for Failure
* View using the Windows Event Viewer


<!--endintro-->

![Enable Auditing for SQL Server loginsNote:  You can turn on a trace for SQL DDL operations statements.](TurnOnSqlSecurityAuditing.png)
