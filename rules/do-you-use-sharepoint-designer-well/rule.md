---
type: rule
title: Do you use SharePoint designer well?
uri: do-you-use-sharepoint-designer-well
created: 2009-04-21T03:07:49.0000000Z
authors:
- id: 8
  title: John Liu
- id: 1
  title: Adam Cogan

---

We love SharePoint designer and use it everyday.

But there are things that it doesn't do naturally, or it does really badly.  Here are some tips on using SharePoint designer well.

- Don't use inline CSS - this goes for any website.
- Always put 
 wrappers around SharePoint controls. This allows us to define styles for SharePoint controls. It is possible to use CssClass like ASP.NET, but then we lose control to SharePoint regarding how that control will be rendered.  Also, some SharePoint controls will eat up your CssClass and not render anything.
- Naming convention for control id! Don't get lazy.
- Turn off Auto indent.  Otherwise SharePoint designer will keep modifying your file whenever it saves the HTML - this will make you very upset.



![Uncheck Auto indent](SPIndent.gif)
