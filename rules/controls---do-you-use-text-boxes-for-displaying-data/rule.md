---
type: rule
title: Controls - Do you use Text Boxes for displaying data?
uri: controls---do-you-use-text-boxes-for-displaying-data
created: 2012-11-27T09:21:17.0000000Z
authors: []

---

 
Use Label controls to display static text of the application. Eg. "Customer ID:"
Use Text Box controls to display data (results of calculations, information, records from a database, etc.).
   ​
The reasons are:

- users know it is data, not a label of the application
- users can copy and paste from the field


PS: One reason web UI's are nice, is that the information is always selectable/copyable.
<dl class="badImage"><dt><img alt="Long string cut off when you are using label" src="http&#58;//www.ssw.com.au/ssw/Standards/Rules/Images/BetterInterface_LabelCutOff.jpg"></dt>
<dd>Figure&#58; Bad Example - Not only is the data cut off when you are using label, but you can't copy and paste the value</dd></dl><dl class="goodImage"><dt><img alt="Using Textbox is better practice" src="http&#58;//www.ssw.com.au/ssw/Standards/Rules/Images/GoodTextbox.gif"></dt>
<dd>Figure&#58; Good Example - Using Textbox controls makes the data obvious to users</dd></dl>
As you can see you'll barely know the difference, so start using Textboxes for displaying data, that's good practice.

#### More Information

When using TextBox controls in Windows Forms, set them up like this:
<dl class="image"><dt><img alt="Using Textbox is better practice" src="http&#58;//www.ssw.com.au/ssw/Standards/Rules/Images/BorderStyle_1.gif"></dt>
<dd>Figure&#58; Having the 'BorderStyle' Property set to Fixed3D is the best choice visually</dd></dl><dl class="image"><dt><img alt="Using Textbox is better practice" src="http&#58;//www.ssw.com.au/ssw/Standards/Rules/Images/ReadOnly_1.gif"></dt>
<dd>Figure&#58; Make the text box Read-Only (users copying data is OK, changing is silly)</dd></dl>
