---
type: rule
title: DBAs - Do you secure your server by changing the 'defaults'?
uri: dbas---do-you-secure-your-server-by-changing-the-defaults
created: 2019-11-21T17:49:51.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

1. Disable defaults
    - Disable Administrator and Rename it, then create a new "honeypot" Administrator account with no permissions.
    - Disable Guest on the SQL
    - Change Port 1433
    - Delete the sample databases - (AdventureWorks, Northwind and Pubs). These have a Public Role which is a security risk and allow Massive SQL Statements
2. Other security issues
    - Use a service account with a strong password
    - Do not run SQL Server service as an administrator
    - Run in integrated security mode
    - Run on NTFS file system - Encrypt the data files
