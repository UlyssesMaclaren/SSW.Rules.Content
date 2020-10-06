---
type: rule
title: Do you only export what is necessary?
uri: do-you-only-export-what-is-necessary
created: 2016-04-28T19:50:49.0000000Z
authors:
- id: 55
  title: Steve Leigh

---

Each file in TypeScript is a module, and each module can export whatever members it wants.  However, if you export everything, you run the risk of having to increment major versions (when using semantic versioning), or having your module used in unintended ways.
 
Only export the types necessary to reduce your API surface.  Often, this means exporting interfaces over implementations.
