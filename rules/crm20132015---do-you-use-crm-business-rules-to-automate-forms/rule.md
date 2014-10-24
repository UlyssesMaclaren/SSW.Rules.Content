---
type: rule
title: CRM2013/2015 - Do you use CRM Business Rules to automate forms?
uri: crm20132015---do-you-use-crm-business-rules-to-automate-forms
created: 2014-10-24T19:03:18.0000000Z
authors:
- id: 32
  title: Mehmet Ozdemir

---

 
Prior to CRM 2013 if a CRM user wanted to:

- Show an error message
- Set a field value
- Set business required
- Set field visibility (show/hide fields)
- Lock or unlock a field


They would normally need to get a CRM developer involved to write JavaScript code to automate these actions.

Starting with CRM 2013 (and much improved in CRM 2015), users can now use Business Rules to automate these actions without getting a CRM developer involved.
 
​​Take the following Example:
<dl class="image"><dt><img src="/Communication/RulesToBetterCRMForUsers/PublishingImages/crm-automated-forms-1.png" alt=""></dt><dd>Figure&#58; ‘Customer Type Other’ should be hidden and only displayed when Other is selected</dd></dl>
To make this work use the following Business Rules:
<dl class="image"><dt><img src="/Communication/RulesToBetterCRMForUsers/PublishingImages/crm-automated-forms-1.png" alt=""></dt><dd>Figure&#58; Show the ‘Customer Type Other’ field when Customer Type equals Other</dd></dl>
The flip side of the expression also needs to be set where Customer Type doesn’t equal Other to hide the ‘Customer Type Other’ field (you could also optionally clear this field too)
<dl class="image"><dt><img src="/Communication/RulesToBetterCRMForUsers/PublishingImages/crm-automated-forms-1.png" alt=""></dt><dd>igure&#58; Hide the ‘Customer Type Other’ field when Customer Type doesn’t equal Other</dd></dl>
Finally the last step is to **Activate** the Business Rules. To activate click the activate button on the top right of the tool bar.

Now the form will look like this:
<dl class="image"><dt><img src="/Communication/RulesToBetterCRMForUsers/PublishingImages/crm-automated-forms-1.png" alt=""></dt><dd>Figure&#58; Great. Now ‘Customer Type Other’ is hidden</dd></dl><dl class="image"><dt><img src="/Communication/RulesToBetterCRMForUsers/PublishingImages/crm-automated-forms-1.png" alt=""></dt><dd>Figure&#58; And on the other side ‘Customer Type Other’ is visible</dd></dl>
**Note:** CRM 2015 further improves on this by introducing the if… else… construct, so instead of creating two business rules (one for show and one for hide), this rule can be reduced to just one.

