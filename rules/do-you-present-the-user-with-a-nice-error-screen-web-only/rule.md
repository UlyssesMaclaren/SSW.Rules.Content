---
type: rule
title: Do you present the user with a nice error screen? (Web Only)
uri: do-you-present-the-user-with-a-nice-error-screen-web-only
created: 2013-09-11T21:08:47.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 38
  title: Drew Robson

---

 
Your users should never see the “yellow screen of death” in ASP.NET. Errors should be caught, logged and a user-friendly screen displayed to the user.
 
This last part is done by adding the  element to the  section of the web.config file.

This will activate ASP.NET’s built in error page (e.g. MVC’s HandleErrorAttribute filter) which can be customized to suit your application.
![](/SoftwareDevelopment/RulesForErrorHandling/PublishingImages/error-screen-bad.jpg)Figure: Bad Example – Yellow Screen of Death![](/SoftwareDevelopment/RulesForErrorHandling/PublishingImages/error-screen-good.jpg)Figure: Good Example - Default ASP.NET MVC custom error page
