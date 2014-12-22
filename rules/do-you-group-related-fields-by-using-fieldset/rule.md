---
type: rule
title: Do you group related fields by using FieldSet?
uri: do-you-group-related-fields-by-using-fieldset
created: 2014-12-22T11:52:59.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
**FieldSet** element allows you to group thematically related controls                     and labels. Grouping controls makes forms more accessible and easier for users to                     understand the purpose of filling the forms.

See the example below using "Your Details"                     and "Event Details".
 <dl class="goodImage"><dt> 
      <img src="/DesignandPresentation/RulestoBetterInterfacesForms/PublishingImages/fieldset.jpg" alt=""> 
   </dt><dd>Figure&#58; Good example - Use FieldSet for grouping</dd><dd></dd></dl>
Here's an example of how FieldSet works:
<dl class="code"><dt><pre>&lt;fieldset&gt;
    &lt;legend&gt;Your Details&lt;/legend&gt;
    &lt;p&gt;
        &lt;label for=&quot;FirstName&quot;&gt;First Name&#58; &lt;/label&gt;
        &lt;input id=&quot;FirstName&quot; type=&quot;text&quot; /&gt;&lt;br /&gt;
        &lt;label for=&quot;LastName&quot;&gt;Last Name&#58; &lt;/label&gt;
        &lt;input id=&quot;LastName&quot; type=&quot;text&quot; /&gt;&lt;br /&gt;
        &lt;label for=&quot;EmailAddress&quot;&gt;Email Address&#58; &lt;/label&gt;
        &lt;input id=&quot;EmailAddress&quot; type=&quot;text&quot; /&gt;
    &lt;/p&gt;
&lt;/fieldset&gt;</pre></dt><dd>Figure&#58; Example code of FieldSet</dd></dl><dl class="image">​ 
   <dt> 
      <img src="/DesignandPresentation/RulestoBetterInterfacesForms/PublishingImages/fieldset-browser.jpg" alt=""> 
   </dt><dd>Figure&#58; How that code will look on the browser</dd><dd></dd></dl>
​ Things to remember:

1. Wrap logical control groups in a &lt;fieldset&gt;.
2. The first child of a &lt;fieldset&gt; should be a &lt;legend&gt;, so the user knows what to expect in that section.

​  
