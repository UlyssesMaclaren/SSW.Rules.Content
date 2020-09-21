---
type: rule
title: Do you Check-in your process template into source control? (legacy)
uri: do-you-check-in-your-process-template-into-source-control-legacy
created: 2012-07-18T07:16:38.0000000Z
authors:
- id: 10
  title: Lei Xu
- id: 78
  title: Matt Wicks

---

 
​For Azure DevOps Server (and old TFS servers)
Note: If using Azure DevOps (cloud) then you have no method of tracking changes to the Process Template​​

The customized process template is a very important asset for your team, you should use Source Control to store the work-in-progress template so you can track the changes and avoid mistakes.
<dl class="image"><dt><img src="CheckInTemplateIntoSourceControl.png" alt="CheckInTemplateIntoSourceControl.png"></dt><dd>Figure: customized process template in source control </dd> </dl>   ​ 
You should also keep a version history log in ProcessTemplate.xml so you can track the deployed version easily.
<dl class="image"><dt><img src="KeepHistoryForTemplate.png" alt="keep history">
   </dt><dd>Figure: ProcessTemplate.xml with version history log​<br></dd></dl>
