---
type: rule
title: Do you swarm to fix the build?
uri: do-you-swarm-to-fix-the-build
created: 2015-11-03T08:46:16.0000000Z
authors:
- id: 37
  title: Ben Cull

---

If you or someone on your team has broken the build, the whole team should swarm to fix the problem immediately. 




It is PERFECTLY ok to have the CI build go red, that is what is there for, but when the build goes red the team should go immediately into corrective action mode and make sure the build goes green again.

Two things should be done:

1. Get it Green
2. Find out WHY it went green locally but red on build server. This may indicate something is brittle in the application structure, and that is the underlying cause – and should of course also be fixed.






![](broken builds.png)

Bad Example: Too many broken builds in a row.



![](good builds.png)
Good Example: Broken build was fixed immediately.
