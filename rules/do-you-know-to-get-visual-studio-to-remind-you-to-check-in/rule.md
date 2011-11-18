---
type: rule
title: Do you know to get Visual Studio to remind you to check in?
uri: do-you-know-to-get-visual-studio-to-remind-you-to-check-in
created: 2011-11-18T03:52:24.0000000Z
authors:
- id: 22
  title: David Klein
- id: 5
  title: Justin King
- id: 17
  title: Ryan Tee
- id: 6
  title: Tristan Kurniawan

---

 This field should not be null (Remove me when you edit this field). 
1. Make Visual Studio remind you to check code in 
In Microsoft Visual Studio. NET sharing project code can be configured by ticking the two checkboxes on top, in Options (from the Tools menu) as shows below.
<dl><dt><img alt="VS.NET 2008 Source Settings" align="middle" src="/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/SourceControlVS.jpg" width="757" height="438"></dt>
<dd>Figure&#58; Check-in files automatically the 2nd checkbox is very important so you get reminded to check-in your project when closing VS.NET. You know how frustrating it is when you want to fix an application and all the files are checked out by some one else! </dd></dl>
**What about VB6 applications ?** 
In Visual Basic 6 this is done by going through Tools -&gt; Source Safe -&gt; Options and setting it as shown in the diagram below.
<dl><dt><img alt="Source Safe VB6" align="middle" src="/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/SourceSafeVB6.gif" width="470" height="222"></dt>
<dd>Figure&#58; You can also check-in automatically in VB6 </dd></dl>
**What about Access applications ?** 
We also use VSS for Access projects. Access 2000 had problems with MDBs (not ADPs) but Access 2003 works fine with both. The only thing you have to be careful of is that if a form is not checked out, it still lets you modify the form, but when you close the form, it rolls back to the VSS version and you lose all of your changes.
<dl><dt><img alt="Source Safe Access" src="/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/SourceSafeAccessOptions.gif" width="482" height="237"></dt>
<dd>Figure&#58; You can also check-in automatically in Access </dd></dl><dl><dt><img alt="Source Safe Access Menu" src="/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/SourceSafeAccessMenu.gif" width="464" height="523"></dt>
<dd>Figure&#58; All the basic functions are easily accessible. </dd></dl>
Note: Using VSS in Microsoft Access has a few limitations, most significant of which is the inability to reattach to VSS projects.  Once you have detached from a VSS project, you will need to create a new VSS project in order to place the Access application back into VSS.

**What about SQL Server Databases?** 
We save the scripts of every SQL Server schema change in Source Control.


