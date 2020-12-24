---
type: rule
archivedreason: 
title: Do you avoid publishing from Visual Studio?
guid: a67b023d-b40f-4619-9d3d-2490f98e153b
uri: do-you-avoid-publishing-from-visual-studio
created: 2013-02-06T18:47:32.0000000Z
authors:
- id: 24
  title: Adam Stephensen
related: []
redirects: []

---

Publishing from Visual Studio is a convenient way to deploy a web application, but it relies on a single developer’s machine which can lead to problems. Deploying to production should be easily repeatable, and able to be performed from different machines.

<!--endintro-->

A better way to deploy is by using a defined Build in TFS.

[[badExample]]
| ![Using Publish to deploy](test-publish.jpg)
[[goodExample]]
| ![Queuing a new build to deploy your application](queuing-new-build.jpg)
![Best example – Use continuous integration to trigger your Continuous Deployment build](continuous-integration.jpg)
