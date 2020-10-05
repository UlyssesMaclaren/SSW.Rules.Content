---
type: rule
title: IP - Do you make your templates accessible to everyone in your organisation?
uri: ip---do-you-make-your-templates-accessible-to-everyone-in-your-organisation
created: 2012-09-25T18:01:13.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 34
  title: Brendan Richards

---

​​​A common mistake is to use code or emails that you have previously written, and stored somewhere on your computer, and change around key bits to make it relevant for the current situation.

The problem with this is that you make it impossible for anyone else in your organization to do the same task to the same quality level.
 
Make sure your company has a common code base and email template store and endeavour​ to improve it regularly. This shares knowledge across your organization and makes sure everyone is working to the level that your company standards require.

### Create Nuget Packages for reusable code libraries

The best approach to reuse code across multiple projects is to create Nuget Packages. When you need to update that library, it is then trivial to apply that update to your client projects.

​​
![](BCE_Nuget_Server.png)
Good Example: when reusing code across multiple projects for a single client, hosting your own Nuget Server provides an excellent way to manage shared private dependencies
For details on creating your own internal Nuget repository, read this rule:[https://rules.ssw.com.au/do-you-create-a-private-repository-for-reusable-internal-code​](/_layouts/15/FIXUPREDIRECT.ASPX?WebId=3dfc0e07-e23a-4cbb-aac2-e778b71166a2&TermSetId=07da3ddf-0924-4cd2-a6d4-a4809ae20160&TermId=91a40442-d5ea-40a5-b442-33419f9fd369)

​

​​
![](SSW_nuget.png)
Good Example: If your library has potential outside of your current requirement, consider publishing to the world on Nuget.  Often the work involved to make a library more generic and re-usable results in better-quality code.
You can find a selection of Nuget packages published by SSW here:
[https://www.nuget.org/profiles/SSW​​](https://www.nuget.org/profiles/SSW)
