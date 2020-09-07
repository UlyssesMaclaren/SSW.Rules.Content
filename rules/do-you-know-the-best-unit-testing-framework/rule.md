---
type: rule
archivedreason: 
title: Do you know the best Unit Testing framework?
guid: 0afc7db0-4f87-4dd9-983d-3f4ebca4fce1
uri: do-you-know-the-best-unit-testing-framework
created: 2017-02-02T18:12:03.0000000Z
authors:
- id: 24
  title: Adam Stephensen
related: []

---

When getting started with unit testing, it is important to use the right tools for the job.

<!--endintro-->
<dl class="badImage">&lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-bad1.png">&lt;/dt&gt;&lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-bad2.png">&lt;/dt&gt;<dd>Bad Example: MS Test was the default testing library for previous versions of .NET and Visual Studio but lacked many features that were available in more complete tools like NUnit<br></dd></dl><dl class="image">&lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-ok1.png">&lt;/dt&gt;&lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-ok2.png">&lt;/dt&gt;<dd>OK Example: NUnit - For previous versions of .NET, NUnit was the best testing library but required work on the Continuous Integration server to get the unit tests to run in a CI environment. One of the key features that NUnit had that MS Test didn't was the TestCase attribute that allows you to specify inline data to be used when invoking that test<br></dd></dl> <dl class="goodImage"> &lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-good1.png">&lt;/dt&gt;&lt;dt&gt;<img src="bestunittest-bad1.png" alt="bestunittest-good2.png">&lt;/dt&gt;<dd>Good Example: XUnit comes out of the box with .NET Core and includes most of the great features of NUnit, while also being supported out of the box with Team Foundation Server and Visual Studio Team Services <br></dd></dl>