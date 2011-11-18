---
type: rule
title: (Before starting) Do you follow a Test Driven Process?
uri: before-starting-do-you-follow-a-test-driven-process
created: 2011-11-18T03:52:57.0000000Z
authors:
- id: 5
  title: Justin King
- id: 6
  title: Tristan Kurniawan

---

 Never allow a situation where a developer can check out code and the code does not compile – or the unit tests are not all green. This is called “breaking the build” and the punishment in our office is 20 push-ups and fixing broken links for an hour! <br> 
**Bad Process**1. Check out
2. Compile
3. Develop
4. Compile
5. Check In

<font class="ms-rteCustom-FigureBad" size="+0">A Bad Developer</font> ![](/TFS/RulesToBetterVersionControlwithTFS(AKASourceControl)/PublishingImages/BeforeCoding.jpg) <font class="ms-rteCustom-FigureNormal" size="+0">Figure&#58; Before you start cooking prepare all your ingredients (aka before you start coding, &quot;Get Latest&quot; the right way)</font>
**Good Process**1. Get latest
2. Compile
3. Run Unit Tests
4. If Tests pass then start developing
5. Check out
6. Develop
7. Compile
8. Run Unit Tests
9. Get Latest (Always do a Get Latest before checking in as code you didn't change could break your code)
10. Compile
11. Run Unit Tests
12. Check In if all tests passed
13. Wait for gated check-in (GC) to complete
14. Reconcile your workspace if it was successful
15. Check that Continuous Integration (CI) build was successful(If GC was skipped)

<font class="ms-rteCustom-FigureGood" size="+0">A Good Developer</font>Note: You should have both a Gated-Check-in (GC) and a Continuous Integration (CI) build on every branch.    
