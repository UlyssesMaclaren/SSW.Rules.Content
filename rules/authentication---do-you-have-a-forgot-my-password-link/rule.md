---
type: rule
title: Authentication - Do you have a 'Forgot my password' link?
uri: authentication---do-you-have-a-forgot-my-password-link
created: 2014-12-11T20:10:16.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 44
  title: Duncan Hunter

---

It's easy and common for users to forget their passwords, the vital key which grants                     them access to the services they are eligible for. To cater for this instance, it                     is important to have a 'Forgot my password' link on the sign in page.
 
[[badExample]]
| ![ what will happen for the poor user that forgot his password?](bad.png)

[[goodExample]]
| ![users have an option if they forget their password](good.png) 

[[goodExample]]
| ![users can enter their email to get a new password](reset example.png) 

### Do you avoid a username enumeration attack?


This practice also opens up the risk of "username enumeration" where an entire collection of usernames or email addresses can be validated for existence on the website simply by batching requests and looking at the responses. You can read more on     [Troy Hunt's blog post](http://www.troyhunt.com/2012/05/everything-you-ever-wanted-to-know.html). You should always aim to not disclose if a user is registered with your site or not.

[[badExample]]
| ![ Displaying information that a user does not exist?](2016-01-05_15-20-06.png)

![](demo.png)Good example - You should always aim to not disclose if a user is registered with your site or not
