---
type: rule
title: Errors – Do you know the daily process to improve the health of your web application?
uri: errors--do-you-know-the-daily-process-to-improve-the-health-of-your-web-application
created: 2014-08-19T00:51:51.0000000Z
authors:
- id: 38
  title: Drew Robson
- id: 45
  title: Chris Briggs

---

 ​​​​​​​Application Insights can provide an overwhelming amount of errors in your web application, so use just-in-time bug processing to handle them.
 
The goal is to each morning check your web application's dashboard and find zero errors. However, what happens if there are multiple errors? Don't panic, follow this process to improve your application's health.
 ![20-08-2014-11-50-59-AM-compressor.png](/PublishingImages/App-Insights-Failures.png) Figure: Every morning developers check Application Insights for errors​

Once you have found an exception you can drill down into it to discover more context around what was happening. You can find out the user's browser details, what page they tried to access, as well as the stack trace (Tip: make sure you follow the rule on [How to set up Application Insights](/_layouts/15/FIXUPREDIRECT.ASPX?WebId=3dfc0e07-e23a-4cbb-aac2-e778b71166a2&amp;TermSetId=07da3ddf-0924-4cd2-a6d4-a4809ae20160&amp;TermId=68f64a3a-78ec-49f6-87ed-7ee92af1c809) to enhance the stack trace).
![](/PublishingImages/App-Insights-Failures-drilldown.png)Figure: Drilling down into an exception to discover more.
It's easy to be overwhelmed by all these issues, so don't create a bug for each issue or even the top 5 issues. Simply create one bug for the most critical issue. Reproduce, fix and close the bug then you can move onto the next one and repeat. This is just-in-time bug processing and will move your application towards better health one step at a time.
![20-08-2014-12-04-31-PM-compressor.png](/PublishingImages/20-08-2014-12-04-31-PM-compressor.png)Figure: Bad example - creating all the bugs ![20-08-2014-12-06-16-PM-compressor.png](/PublishingImages/20-08-2014-12-06-16-PM-compressor.png) Figure: Good example - create the first bug (unfortunately bug has to be created manually)
 
