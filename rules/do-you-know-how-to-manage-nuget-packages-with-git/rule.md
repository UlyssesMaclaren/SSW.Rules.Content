---
type: rule
title: Do you know how to manage NuGet packages with Git?
uri: do-you-know-how-to-manage-nuget-packages-with-git
created: 2014-10-23T04:30:48.0000000Z
authors:
- id: 38
  title: Drew Robson
- id: 44
  title: Duncan Hunter

---

 ​Do you know the best way to manage NuGet packages with Git? You can get into all sorts of trouble including your packages in source control. 
You can get into all sorts of trouble including your packages in source control. The following are a few issues that are related to having your NuGet packages in source control:

1. Over time the packages will grow to be too many and cloning the repository will be slow.
2. You could get duplicate NuGet packages in your packages folder as new versions are updated.
3. NuGet shows packages to update that have already been updated. This can happen if you have duplicate NuGet packages but are different versions.
4. It becomes harder to "clean" your solution of any unused package folders, as you need to ensure you don't delete any package folders still in use.


​

How to remove your NuGet packages from the repository using NuGet Package Restore

1. ​Read the NuGet offical documentation here http://docs.nuget.org/docs/reference/package-restore
2. Complete the following steps to activate NuGet Package and include repositories.config in source control. With this done the NuGet Visual Studio extension integrates into Visual Studio's build events and restores missing packages when a build begins.
3. Go to Team Explorer in Visual Studio and select Settings![Team explorer home 2014-10-23_14-39-49.png](/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Team%20explorer%20home%202014-10-23_14-39-49.png)​
4. Choose Git Settings under Git![Team-Explorer-2014-10-23_14-40-48-compressor.png](/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Team-Explorer-2014-10-23_14-40-48-compressor.png)
5. 




![Bad example 2014-10-22_17-15-18.png](/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Bad%20example%202014-10-22_17-15-18.png)

<dd class="ssw15-rteElement-FigureBad">​Figure&#58; Bad Example - Duplicate NuGet packages in the packages folder</dd>​​



![good example  2014-10-22_17-03-59.png](/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/good%20example%20%202014-10-22_17-03-59.png)
<dd class="ssw15-rteElement-FigureGood">Figure&#58; ​​<span style="color&#58;#555555;font-size&#58;11px;font-weight&#58;bold;line-height&#58;16px;">Good Example – No duplicate packages in the packages folder</span><br></dd>




