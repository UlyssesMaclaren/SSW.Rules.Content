---
type: rule
title: Do you keep the best possible bug database?
uri: do-you-keep-the-best-possible-bug-database
created: 2009-02-28T09:44:02.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 There are 101 bug databases on the market at the moment and of course many companies make up their own in-house system.<br> ![](/Management/RulesToSuccessfulProjects/PublishingImages/bugs.jpg)
This is a common scenario: Your tester/client finds a bug, they log on to your on-line bug database, and enter the data, they save the error message as a gif and upload the image. As Project Manager, you get notified by email of the bug, you log on to the application, view the image, review the status, assign a priority, and assign it to a developer. The developer receives the email, logs on and sets about fixing the bug. When completed, he logs back on to the application, enters a completed date, and an email is sent to the tester/client. The tester/client logs on, and is told what to test, reviews the work, enters a checked by date, and the final email is sent to the manager who closes the bug.

Phew! That sounds like a lot of steps which is why most people resort to just sending an email. I believe most people send requests for tasks via email, if this is the case, why should developers have a separate "to-do" list, in the form of a bug-database in which they re-enter data?

Exchange Server and Public Folders (made available on the Internet) are an alternative solution. The benefits are:

- Developers are working solely from their email which they are familiar with, and don't have to switch applications when working on their "to-do" list
- They don't have to re-enter data
- Managers can see important information like Tasks Completed and Tasks Assigned. The reports are ASPX pages that read from Exchange Server via OLEDB
- Clients can see what developers are working on via a URL to the Public Folder





| You can build your own solution or use [SSW eXtreme Emails!](http&#58;//www.ssw.com.au/ssw/ExtremeEmails/Default.aspx)  |
| --- |

 SSW now uses TFS to manage bugs rather than eXtreme Emails, but we still allow clients to just send us an email.   
