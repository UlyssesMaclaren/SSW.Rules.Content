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

 ​​​​Do you know the best way to manage NuGet packages with Git? You can get into all sorts of trouble by including your packages in source control. 



The following are a few issues that are related to having your NuGet packages in source control:

1. Over time the packages will grow to be too many and cloning the repository will be slow.
2. You could get duplicate NuGet packages in your packages folder as new versions are updated.
3. NuGet shows packages to update that have already been updated. This can happen if you have duplicate NuGet packages but they are different versions.
4. It becomes harder to "clean" your solution of any unused package folders, as you need to ensure you don't delete any package folders still in use.







Automatic Package Restore in Visual Studio 

Beginning with NuGet 2.7, the NuGet Visual Studio extension integrates into Visual Studio's build events and restores missing packages when a build begins. This feature is enabled by default but you will need to include packages.config​ in your source control.





Here's how it works:



1. On project or solution build, Visual Studio raises an event that a build is beginning within the solution.
2. NuGet responds to this event and checks for packages.config files included in the solution.
3. For each packages.config file found, its packages are enumerated and checked for existence in the solution's packages folder.
4. Any missing packages are downloaded from the user's configured (and enabled) package sources, respecting the order of the package sources.
5. As packages are downloaded, they are unzipped into the solution's packages folder.​




You can read more here [http://blogs.msdn.com/b/dotnet/archive/2013/08/22/improved-package-restore.aspx?PageIndex=3#comments](http&#58;//blogs.msdn.com/b/dotnet/archive/2013/08/22/improved-package-restore.aspx?PageIndex=3#comments).

​

If you are using a version of NuGet prior to version 2.7 then the below steps outline how to avoid including packges in source control :

1. ​Read the [offical NuGet documentation​](http&#58;//docs.nuget.org/docs/reference/package-restore)
2. Enable NuGet Package Restore for your solution by right clicking on your solution name in the Solution Explorer and select Enable NuGet Package Manage Restore from the drop down menu.<br>   <dl class="image"><dt><img src="/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Enable%20package%20restore%202014-10-23_17-43-13.png" alt="nuget package restore2.png" style="width&#58;489px;"></dt></dl>
3. Go to Team Explorer in Visual Studio and select Settings.<br>   <dl class="image"><dt><img src="/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Team%20explorer%20home%202014-10-23_14-39-49.png" alt="Team explorer home">​</dt></dl>
4. Choose Git Settings under Git. <br>   <dl class="image"><dt><img src="/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Team-Explorer-2014-10-23_14-40-48-compressor.png" alt="Team-Explorer compressor"></dt></dl>
5. Choose /.gitIgnore<br>   <dl class="image"><dt><img src="/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/Git%20Settings%202014-10-23_14-41-22.png" alt="Git Settings"></dt></dl>
6. In the gitIgnore file find and uncomment the repositories.config line to include it in source control.<br>   <dl class="image"><dt><img src="/TFS/RulesToBetterVersionControlWithGit/PublishingImages/Pages/Do-you-know-how-to-manage-NuGet-packages-with-Git/git-ignore-image-2014-10-23_14-27-55-compressor.png" alt="git-ignore-image-compressor.png" style="width&#58;550px;"></dt></dl>
7. rebuild your solution and you can now safely delete your packages folder and NuGet Package Restore will restore any missing NuGet packages on each new build. You will not need to add your package folder to your repository after these steps.​​​​​​

<br>​

