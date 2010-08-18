---
type: rule
title: Do you know common web configuration stuff you will need?
uri: do-you-know-common-web-configuration-stuff-you-will-need
created: 2009-06-16T01:41:30.0000000Z
authors:
- id: 8
  title: John Liu
- id: 18
  title: Jay Lin

---

  In SharePoint, web configuration includes:<br>
1. ASP.NET 3.5 library references – this is necessary for all the ASP.NET AJAX calls
2. Add system.web/pages/controls – to add additional tag prefix from System.Web.Extensions
3. Add HttpModule (for example – to clean up extra JavaScript from SharePoint)
4. SafeControl tags for all custom dlls – in general these can be added via your solution package as well


You should always use a SPConfigModification class to modify your web.config – never tell your user or administrator to make changes manually!  This also allows them to switch off a feature from SharePoint knowing that the changes had been reverted.
For developers – you must test your SPConfigModification carefully, mismatched XPath will cause problems in your web.config and create duplicate entries!
