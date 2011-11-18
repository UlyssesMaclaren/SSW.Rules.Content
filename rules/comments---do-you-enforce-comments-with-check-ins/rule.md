---
type: rule
title: Comments - Do you enforce comments with check-ins?
uri: comments---do-you-enforce-comments-with-check-ins
created: 2011-11-18T03:52:40.0000000Z
authors:
- id: 22
  title: David Klein
- id: 5
  title: Justin King
- id: 17
  title: Ryan Tee
- id: 6
  title: Tristan Kurniawan
- id: 38
  title: Drew Robson

---

 This field should not be null (Remove me when you edit this field). ![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/CommentsBad.jpg) <font class="ms-rteCustom-FigureBad" size="+0">Figure&#58; Bad Example&#58; No Comments against the check-ins we don’t know what changes were made in each revision </font>![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/CommentsGood.jpg) <font class="ms-rteCustom-FigureGood" size="+0">Figure&#58; Good Example&#58; Now we can pin point which revision a particular change has been made </font>
More Information 
 To enforce this behaviour, you will need to:

1. Install Team Foundation Server Power Tools
2. Right click the Team Project in Team Explorer &gt; Team Project Settings &gt; Source Control ![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/Enforce1.jpg)
3. Select the Check-in Policy tab
4. Click Add
5. Select the Changeset Comments Policy 
![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/Enforce2.jpg)

 Now the next time someone checks-in some code, they are forced to enter a comment.   
