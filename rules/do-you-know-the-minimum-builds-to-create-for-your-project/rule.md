---
type: rule
title: Do you know the minimum builds to create for your project?
uri: do-you-know-the-minimum-builds-to-create-for-your-project
created: 2011-11-18T03:52:49.0000000Z
authors:
- id: 22
  title: David Klein
- id: 6
  title: Tristan Kurniawan
- id: 17
  title: Ryan Tee
- id: 5
  title: Justin King
- id: 23
  title: Damian Brady

---

 
When creating projects one of the only ways that you have of proving that it works and is a viable solution is to build it. This is easy when you only have one developer and that developer will be the only one using a solution. But what if you have 2 developers? How do you prove that one developer's code works with the other? The answer is build servers. These build servers take specific code away to another computer and build it there.

You should always have three builds on your team project. These should be setup and tested using an empty solution before you write any code at all.
 ![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/Builds.jpg) Figure: Three builds named in the format [TeamProject].[AreaPath]\_[Branch].[Gate|CI|Nightly] for every branch. These builds should use the same XAML build workflow; however you may set them up to run a different set of tests depending on the time it takes to run a full build. 

- **Gate** - Only needs to run the smallest set of tests, but should run most if not all of the Unit Test. This is run before developers are allowed to check-in (a gated Check-in)
**Note: **This build should take no more than 2 minutes otherwise developers will get annoyed!
- **CI** - This should run all Unit Tests and all of the automated UI tests. It is run after a successful developer check-in.
**Note:** This build should take no more than 10 minutes to run.
- **Nightly** - The Nightly build should run all of the Unit Tests, all of the Automated UI tests and all of the Load and Performance tests. The nightly build is time consuming and will run but once a night. Packaging of your Product for testing the next day may be done at this stage as well.
**Note:** This build can take as long as it needs to - of course more than 24 hours is too long.

![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/ControlTestAndData.jpg) Figure: You can control what tests are run and what data is collected while they are running. Note: We do not run all the tests every time because of the time consuming nature of running some tests, but ALL tests should be run overnight. 
Note: If you had a really large project with thousands of tests including long running Load tests you may need to add a Weekly build to the mix. 
![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/BuildStatus01.jpg) Figure: Bad example, you can't tell what these builds do if they are in a larger list ![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/BuildStatus02.jpg)Figure: Good example, you know exactly what project, branch and type of build these are for. 
