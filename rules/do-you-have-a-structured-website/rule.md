---
type: rule
title: Do you have a structured website?
uri: do-you-have-a-structured-website
created: 2016-08-03T18:48:19.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
The following structure allows you to keep your website clean of clutter:​
 
- **/Images** - for all static images
- **/Images/Dynamic** - for all images used in dynamically generated pages 
NOTE: the reason we use two images directories is so we can exclude images used by dynamically generated pages from our link checking program. This is so we can work out the TRUE orphan images (and believe me, like coat-hangers they multiply quickly ...)
- **/Includes** - for all include files
- **/Bin **- for mdb's, dll's and udl's
- **/Shop** - for the shopping basket and related pages
- **/Clients** - for the client login page and related pages
- **/Reports **- for any SQL Server Reporting Services
- **/zsMaintenance **- for the administration section to modify web site settings
- **/zsValidate** - for all web server status and validation checks


The root directory should be clean, having only:

- **default (.aspx, .asp, .htm)**
- **global.asa**
- **application.sln ​**




