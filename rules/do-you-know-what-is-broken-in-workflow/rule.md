---
type: rule
title: Do you know what is broken in workflow?
uri: do-you-know-what-is-broken-in-workflow
created: 2009-06-16T01:59:00.0000000Z
authors:
- id: 8
  title: John Liu
- id: 18
  title: Jay Lin

---


SharePoint comes with some very basic workflows out of the box.  A particular example is the content approval workflow.

When a content approval workflow is used, it modifies the process of publishing content to be:

1. User clicks publish (click 1)
2. Workflow starts, and asks the user to request for approval, there’s an option to add additional messages (click 2)
3. The workflow sends an email to the user to tell him an approval workflow has started. (email 1)
4. The workflow also sends an email to the approver(s) (email 2)
5. The approver receives an email, then returns to the page – they can Approve or Reject the workflow. (click 3)
6. Either way, a new workflow screen appears, with an option to add additional messages, the approver clicks accept (click 4)
7. The approval workflow completes and publishes the page.
8. It then sends an email telling the user that an approval workflow has been completed (email 3).


What is the problem?

The out of the box workflow is extremely generic.  It has no customizations or shortcuts.  Even if you are an approver, you cannot skip any of the steps.  The end result is that you will have to click 4 times and receive 3 emails, for approving your own finalized content.

These kind of workflows are designed generic to fit any business’ needs – and in fact, businesses using these out of the box workflows have to adjust their staff’s workflow to match SharePoint’s ones.  Which can be counter intuitive.





We think these SharePoint workflows need to be far more customizable.

SharePoint does not provide support for complex reusable workflows easily - most companies go for a 3rd party solution:
![](Blackpearl.png) Figure: 3rd party tool - Blackpearl<br>    ![](Ninetex.png) Figure: 3rd party tool - Nintex 
