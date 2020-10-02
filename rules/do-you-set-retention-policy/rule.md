---
type: rule
title: Do you set retention policy?
uri: do-you-set-retention-policy
created: 2016-05-30T06:41:05.0000000Z
authors:
- id: 46
  title: Danijel Malik

---

Octopus Deploy will by default keep all packages (NuGet, ZIP, …) as well as files deployed on all Tentacles. Because of that your hard drive will fill up very fast as you keep pushing in more packages and creating more releases, especially if you are using Continuous Integration and pushing out new packages with every commit to a repository.
   That's why you need to set up a retention policy. Octopus Deploy supports two options:

- Retention policy for packages
- Retention policy for deployments (via Lifecycle phases)

You should set up both.



### Package Policy




![](2016-05-30_15-00-04.png)

Bad<br>Example - Retention policy is set to Keep forever


![](2016-05-30_15-00-29.png)
Good<br>Example - Retention policy is set to a number of days


### Lifecycle Policy


![](2016-05-30_15-01-55.png)
Bad<br>Example - Lifecycle's retention policy is set to Keep all


![](2016-05-30_15-49-37.png)
Good<br>Example - Lifecycle's retention policy is set to 3 Releases
