---
type: rule
title: Do you reference the issue ID when writing a test to confirm a bugfix?
uri: do-you-reference-the-issue-id-when-writing-a-test-to-confirm-a-bugfix
created: 2020-03-11T20:48:03.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

Some bugs have a whole histroy related to them and when we fix them we don't want to lose the rationale for the test. By adding a comment to the test, referencing the bug ID - future developers can see why a test is testing a particular behaviour.
 
​[Test]
public void TestProj11()
{
}
Figure: Bad example - The test name is the bug ID and I don't know what it is meant to test​​​

///
 Test case where a user can cause an application exception on the
 Seminars webpage
 1. User enters a title for the seminar
 2. Saves the item
 3. Presses the back button
 4. Chooses to resave the item
 See: https://server/jira/browse/PROJ-11
 ///
[Test]
public void TestResavingAfterPressingBackShouldntBreak()
{
}
Figure: Good example - The test name is clearer, good comments for the unit test​​​ give a little context, and there is a link to original bug
