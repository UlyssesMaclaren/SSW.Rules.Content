---
type: rule
archivedreason: 
title: Do you avoid using “any”?
guid: aec54975-ddf2-421c-ae6d-0964f7e02b0b
uri: do-you-avoid-using-any
created: 2016-04-28T19:32:36.0000000Z
authors:
- id: 55
  title: Steve Leigh
related: []

---

TypeScript’s any keyword is a blessing and a curse.  It is a type that can be anything, where every possible property and method exists and also returns any. It can be casted to and from anything and is how you tell the compiler to get out of your way.

However, it’s easy to use it as a crutch, and as a result, miss out on handy intellisense, refactoring support and compile-time safety – the main benefits of TypeScript!

<!--endintro-->

Aim to use any in the same way that you use the dynamic keyword in C# - that is, sparingly, and with careful consideration.
<dl class="badImage">&lt;dt&gt;<img src="any-bad.png" alt="any-bad.png" data-pin-nopin="true">&lt;/dt&gt;<dd>Figure: Bad example – I can pass anything into this method, so I get bad output at run time (“undefined undefined”)</dd></dl><dl class="goodImage">&lt;dt&gt;<img src="any-good.png" alt="any-good.png">&lt;/dt&gt;<dd>Figure: Good example – using types means I get errors and intellisense support </dd></dl>