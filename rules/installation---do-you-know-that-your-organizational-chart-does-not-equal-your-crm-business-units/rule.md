---
type: rule
title: Installation - Do you know that your organizational chart does not equal your CRM Business Units?
uri: installation---do-you-know-that-your-organizational-chart-does-not-equal-your-crm-business-units
created: 2012-12-10T17:59:51.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
Usually there is not much point creating an over-complicated organizational structure in MSCRM, a flatter organizational chart will achieve the same end result. Whilst the security model of Microsoft CRM is highly configurable, most organizations do no need to have excessive differentiation of data ownership and hence could cut down on unnecessary work. It is recommended to use the "out of the box" roles for almost all organizations less than 30 users.
![Microsoft CRM Default Security Roles are good enough to start with](CRM-Default-Role.jpg)Figure: Microsoft CRM Default Security Roles are good enough to start with - this is not a thing to stuff with early on
First thing first... **never** delete an Out of the Box (OOTB) role. Instead just disable... Period. The reason is it can cause system instability when the only solution can be to start from scratch with a New Organization.

CRM Roles and Business Units (BUs) are related but quite separate in concept. When designing security roles, there are two schools of thought - job function oriented and functional task oriented. Hybrid model is commonly seen as well.

BU's don't normally equate to an Organization Chart in real life, and more often than you might realize.

Considerations when designing BU's:

- Security
- Data ownership
- Operations and collaborations
- Business functions
- Geographical locations


In CRM 2011, two new features help in simplifying security design:

1. Multiple forms per entity can be assigned to different security roles
2. Field level security to add to the next level of security granularity


