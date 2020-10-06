---
type: rule
title: Do you know not to delete expired domain users?
uri: do-you-know-not-to-delete-expired-domain-users
created: 2014-09-03T19:35:18.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

When an employee leaves or a domain account expires, disable the account, never delete it, as:

- Some LOB application such as CRM maintain a reference to the AD domain user GUID
- During the migration or restoration of CRM, users stored in the database are verified against AD and problems may occur if they no longer exist
