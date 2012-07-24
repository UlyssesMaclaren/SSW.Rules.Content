---
type: rule
title: Do you separate JavaScript functionality (AKA Unobtrusive JavaScript)?
uri: do-you-separate-javascript-functionality-aka-unobtrusive-javascript
created: 2012-07-24T18:09:29.0000000Z
authors:
- id: 16
  title: Tiago Araujo

---

 
A website can be broken down into three main development parts: content, design and functionality. To optimize a website for search engines, it's important to separate the content  (crucial for search engines) from design and functionality (not important for SEO).
 
All JavaScript code should go into an external .js file (linked to the document with a &lt;script&gt; tag in the head of the page) and not embedded within HTML. The same should be done for CSS files. Don't bloat your HTML file and confuse search engines. Separate the legitimate content from what is programming code.


&lt;a onclick="action()" href="#"&gt;Click Here&lt;/a&gt;

Figure: Never include Javascript as inline attributes

&lt;a href="backuplink.html" class="action"&gt;Click Here&lt;/a&gt;

Figure: Javascript (included in an external file) should use a class or id for its behaviours
