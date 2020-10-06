---
type: rule
title: Do you know what errors to filter out?
uri: do-you-know-what-errors-to-filter-out
created: 2016-10-25T16:49:58.0000000Z
authors:
- id: 3
  title: Eric Phan

---

You should always keep on top of your RayGun crashreporting and not let the errors spiral out of control. If use RayGun with a web application, then you’ll frequently get a lot of errors with robots scanning the site and creating 404s.  
  
[[badExample]]
| ![Most of these errors are 404s cause by automated tools scanning for vulnerabilities](raygun-fileter-bad.png)
Luckily RayGun has built-in filtering to hide these frequent exceptions.
 
![](raygun-filter.png) 
To enable filtering:

1. Under  **Crash Reporting**  > select  **Filtering**
2. SSW recommends you turn on the following rules
    1. Discard any requesters where the user-agent is a known crawler bot
    2. Discard any request for non-existent resources (404)
    3. Discard any requests related to phpMyAdmin access attempts


Now you should have a nice clean crash report page with actual errors.
 
[[goodExample]]
| ![Now that the noise is gone, we can see the actual errors](raygun-filter-good.jpg)
