---
type: rule
title: Controls - Do you use the fonts recommended by Microsoft in your application? (Windows Forms Only)
uri: controls---do-you-use-the-fonts-recommended-by-microsoft-in-your-application-windows-forms-only
created: 2012-11-27T09:16:16.0000000Z
authors: []

---

Some font are easier to read then others, at SSW we follow Microsoft's [Visual Design Guidelines](http://www.ssw.com.au/ssw/Redirect/Microsoft/MSDNInterfaceText.htm). This means we use Tahoma 8pt as our font of choice.
 
At SSW, we use Code Auditor to ensure all fonts on our forms are set to Tahoma but we allow controls to use a different font. This is because certain information is better displayed in a different font. For example a Textbox to show code should use Courier instead of Tahoma.
![ Bad Example - This form uses a non-standard font, and it is hard to read![Form with Tahoma Font](../assets/FontGoodTahoma.gif)](../assets/FontBadArialNarrow.gif)

| We have a program called [SSW Code Auditor](http://www.ssw.com.au/ssw/CodeAuditor/Rules.aspx#VBFont) to check for this rule. |
| --- |
