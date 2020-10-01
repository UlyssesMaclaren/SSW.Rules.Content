---
type: rule
title: Do you do a quick test after the upgrade finishes?
uri: do-you-do-a-quick-test-after-the-upgrade-finishes
created: 2015-08-14T11:31:19.0000000Z
authors: []

---

After upgrading TFS, you should do a quick [smoke test](http://en.wikipedia.org/wiki/Smoke_testing)   to ensure TFS is running as expected.
 
![ New TFS Title using our existing url](tfs title.png)

a.      Navigate to the web access URL for your new TFS server.

b.     If it loads correctly, click "Browse all..." to check all your Team Projects were migrated across correctly

c.      In Visual Studio, connect to TFS, then:

.                Do a Get Latest on a project or file

Make a change, and ensure you can Check In
