---
type: rule
title: Do you use Group Policy to Apply Settings to all of your Cluster Nodes?
uri: do-you-use-group-policy-to-apply-settings-to-all-of-your-cluster-nodes
created: 2012-03-02T18:43:20.0000000Z
authors: []

---

Don't log in and make manual changes to the clustered nodes.

When working with clustered environments it is important that settings be consistent across every node. The best way to handle this is through group policy.
 
Create a policy that you would like applied to each node of the cluster using the **Group Policy Management**.
![ Bad Example - Do not manually change settings on each node![Group policy good](group-policy-good.jpg)](group-policy-bad.jpg)
