---
type: rule
title: C#/VB.NET Configuration - Do you know not to use debug compilation in production applications?
uri: cvbnet-configuration---do-you-know-not-to-use-debug-compilation-in-production-applications
created: 2013-01-11T18:25:53.0000000Z
authors: []

---

 
Debug compilation considerably increases memory footprint since debug symbols are required to be loaded.

Additionally it will hit the performance because that will include the optional debug and trace statements in the output IL code.

In debug mode the compiler emits debug symbols for all variables and compiles the code as is. In release mode some optimizations are included:

- unused variables do not get compiled at all
- some loop variables are taken out of the loop by the compiler if they are proven to be invariants
- code written under #debug directive is not included etc.


The rest is up to the JIT.

As per:     [C# debug vs release performance](http&#58;//stackoverflow.com/questions/2446027/c-sharp-debug-vs-release-performance).
![](/SoftwareDevelopment/RulesToBetterDotNETProjects/PublishingImages/debug-bad.jpg)Figure: Bad Example![](/SoftwareDevelopment/RulesToBetterDotNETProjects/PublishingImages/debug-good.jpg)Figure: Good Example
