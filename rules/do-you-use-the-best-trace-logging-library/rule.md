---
type: rule
title: Do you use the best trace logging library?
uri: do-you-use-the-best-trace-logging-library
created: 2013-09-11T21:38:08.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 38
  title: Drew Robson
- id: 34
  title: Brendan Richards

---

 
Did you know that writing your own logging infrastructure code wastes time? You should use a logging library, and the best logging library is Serilog.

Serilog is a NuGet package that can be included in any .Net application, is easy to configure, supports many different output targets, has great performance, and allows for runtime changes to configuration. Serilog also supports full integration with log4net so is easy to use with any older codebase using log4net.
 
Serilog supports all the log4net concepts of logging at different levels of importance (e.g. Error, Warning, Information) and having different logs for different components of your application (e.g. a Customer Log and an Order Log).

Serilog's main advantage over previous loggers is its ability to serialize and log full .net objects rather than just strings. Serilog also has a powerful, nested context system allowing log events to be grouped by request, operation etc.

Serilog has the concept of "sinks": pluggable modules that that can consume, store and/or act on logging events. The most pwerfult sink is Seq - a web aplication that allows the user to perform complex search queries on incoming log data in real time.

Other sinks allow you to:

- ​save logs to a file
- export to log4net (and subsequently use any log4net appender)
- save to a database
- export to Application Insights, New Relic and many other APM platforms


Many other sinks are available as described here: [https://github.com/serilog/serilog/wiki/Provided-Sinks​](https&#58;//github.com/serilog/serilog/wiki/Provided-Sinks)
![](/PublishingImages/trace-logging-bad.jpg)Figure: Bad Example - Using Debug or Trace for logging, or writing hard coded mechanisms for logging does not allow you to configure logging at runtime![](/PublishingImages/trace-logging-bad-2.jpg)Figure: Bad Example - Roll your own logging components lack functionality, and have not been tested as thoroughly for quality or performance as log4net
​

![serilog.png](/PublishingImages/serilog.png)
Figure: Good Example - Using serilog allows persisting stuctured log data to multiple<br>stores, querying that data intelligently and requires less work to install and configure than a roll-you-own logger, and provides many more features
![seq2.png](/PublishingImages/seq2.png)
Figure: Good Example - Seq provides a powerful UI for searching and viewing your structured logs
Serilog should be added to your project via the NuGet package manager.

See also [Do you use the best middle tier .Net libraries?](/_layouts/15/FIXUPREDIRECT.ASPX?WebId=3dfc0e07-e23a-4cbb-aac2-e778b71166a2&amp;TermSetId=07da3ddf-0924-4cd2-a6d4-a4809ae20160&amp;TermId=9ea489f4-032b-4e5b-a0e0-df5a0c3148fe)

