---
type: rule
title: Do you have a Validation page (the /zsValidate) for your web server?
uri: do-you-have-a-validation-page-the-zsvalidate-for-your-web-server
created: 2016-11-16T16:43:56.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

How can you know that all components are working correctly on your site? It is vitally important to have a 'Health Check' page to validate everything is working correctly. This page will check the server and make sure:

- all the DLLs are present (and registered for COM ones)
- all the web services are working
- all the databases are alive, etc.


 
![ ](../../assets/la-footer.jpg)
[Link Auditor](https://sswlinkauditor.com/) server info
You would be surprised how many dependencies a large web page can have.The advantage of this page is if you ever need to redeploy your application on another server or you have some pages that are just not working as planned you can load up this page and get a quick diagnostics of your website.

![ One of the components on this web site is down](../../assets/ValidateSetup.jpg)

![ Automatically validating our website](../../assets/ValidationTests.jpg)

See [SSW Rules - Do you have a zsValidate page to test your website dependencies?](https://www.ssw.com.au/ssw/Standards/Rules/RulesToBetterUnitTests.aspx#zsValidatePage)
<br>​​
