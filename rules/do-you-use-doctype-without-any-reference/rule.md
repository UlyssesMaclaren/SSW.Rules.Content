---
type: rule
title: Do you use DOCTYPE without any reference?
uri: do-you-use-doctype-without-any-reference
created: 2014-12-15T17:59:16.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 16
  title: Tiago Araujo

---

Since HTML5, DOCTYPE no longer requires a reference to a DTD. Back in HTML 4.01, The DTD links were used in to specify the rules for the markup language (Transitional, Strict, Frameset etc) so that the browsers render the content correctly. It’s no longer necessary.    
&lt;!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "[http://www.w3.org/TR/html4/strict.dtd](http&#58;//www.w3.org/TR/html4/strict.dtd)"&gt;
Figure: Bad Example – XXX
&lt;!DOCTYPE html&gt;
Figure: Good Example – XXX
For more information, go to <br>      [HTML !DOCTYPE Declaration on w3schools.com](http&#58;//www.w3schools.com/tags/tag_doctype.asp)
