---
type: rule
archivedreason: 
title: Do you avoid Double-Negative Conditionals in if-statements?
guid: 994524f4-cb01-4dbb-b2fa-0fea1642839f
uri: do-you-avoid-double-negative-conditionals-in-if-statements
created: 2018-04-24T22:03:21.0000000Z
authors:
- id: 1
  title: Adam Cogan
related: []

---

Try to avoid Double-Negative Conditionals in if-statements. Double negative conditionals are difficult to read because developers have to evaluate what is positive state of two negatives. So always try to make a single positive when you write if-statement.

<!--endintro-->

if (!IsValid)
{
 // handle no error
}
else
{
 // handle error
}




::: bad
Figure: Bad example

:::


if (IsValid)
{
 // handle error
}
else
{
 // handle no error
}




::: good
Figure: Good example

:::


if (!IsValid)
{
 // handle error
}


::: good
Figure: Another good example
:::