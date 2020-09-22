---
type: rule
title: ​DBAs - Do you name your SQL Server Domain Account as 'SQLServerMachineName' so it is easily identified when performing network operations?
uri: dbas---do-you-name-your-sql-server-domain-account-as-sqlservermachinename-so-it-is-easily-identified-when-performing-network-operations
created: 2019-11-18T23:37:45.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
​​When you create the domain accounts under which SQL Server services run, you should name this domain account as "SQLServerMachineName".

E.g. **SSW2000\SQLServerDragon**

If one of the SQL Server services updates a file on the network, then you can then determine which server wrote to the file.​
 
