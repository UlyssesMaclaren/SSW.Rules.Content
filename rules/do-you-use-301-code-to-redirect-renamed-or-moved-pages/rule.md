---
type: rule
title: Do you use "301" code to redirect renamed or moved pages?
uri: do-you-use-301-code-to-redirect-renamed-or-moved-pages
created: 2015-11-09T19:16:40.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 16
  title: Tiago Araujo

---

Don't lose your Google juice when you rename a file. Do not use META refresh to redirect pages - "301" code is the most efficient and Search Engine Friendly method for webpage redirection. There are different ways to implement and it should preserve your search engine rankings for that particular page. If you have to change file names or move pages around, always use the code "301", which is interpreted as "moved permanently".
 
### How to do a "301" redirect in .aspx

Any time you move a page or just delete a page you should add a "301" redirect to a new page or a page for missing pages.

1. You can add a 301 redirect in code    &lt;% Response.RedirectPermanent("NEW PAGE URL HERE") %&gt;
Although this works well it is difficult to manage the list of redirects and you need to keep the page around.
2. **You can write an HTTP handler**
This is better as you can choose where to store the redirect list, but you still need to manage a custom codebase.
3. **You can use rewrite maps in IIS URL Rewrite to add a number of redirects** 
See Storing URL rewrite mappings in a separate file  for an explanation of how to use rewrite maps.

**Note:** If you are using a source control, like TFS, lock the old file so no-one can edit it by mistake.

### WordPress 


WordPress automatically redirects posts when you change the URL (permalink). No further action is required.
