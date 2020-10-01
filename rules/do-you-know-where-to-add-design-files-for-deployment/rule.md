---
type: rule
title: Do you know where to add design files for deployment?
uri: do-you-know-where-to-add-design-files-for-deployment
created: 2009-04-20T00:13:00.0000000Z
authors:
- id: 8
  title: John Liu

---

When a designer (or a developer) adds design/style files to SharePoint - care must be taken regarding where the files are placed:

- Some places are are not suitable because they are not good for deployment
- Other places may have permission issues - designers can't access them
- Some files are part of the site definition and should not be customized


So our rules are:

1. Never modify out of the box SharePoint files in /Style Library/ - those files are part of the site definition, if you customize them they are hard to deploy
2. Start with a clean, minimal masterpage
3. Create and reference your own CSS files and put them under /Style Library/CSS/&lt;client&gt;/
4. You may want to further divide your CSS paths according to the areas of the site that your CSS is designed for:
<br>    E.g. /Style Library/CSS/SSW/Clients/layout.css
5. Designers can modify the XSL file as well!
<br>    put them under /Style Library/XSL Style Sheets/&lt;client&gt;/
