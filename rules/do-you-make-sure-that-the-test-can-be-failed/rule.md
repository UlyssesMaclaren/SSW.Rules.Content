---
type: rule
title: Do you make sure that the test can be failed?
uri: do-you-make-sure-that-the-test-can-be-failed
created: 2020-03-12T23:16:37.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 81
  title: Jason Taylor

---

You should make sure that the unit tests you create can actually fail. A test that never fails is not useful to anyone.

This is a fundamental principle in Test Driven Development (TDD) called Red/Green/Refactor.
 
A common approach is by returning NotImplementedException() from the method you are writing tests for. For Example:

[Test]
public void ShouldAddTwoNumbers()
{
   var calculator = new Calculator();
   var result = calculator.Sum(10, 11);


   Assert.Equal(21, result);
}

// The method to test in class Calculator ...
public int Sum(int x, int y)
{
   throw new NotImplementedException();
}
Bad Example: The test fails by throwing a NotImplementedException

This test fails for the wrong reason, by throwing a NotImplementedException. In production, this is not a valid reason for this test to fail.

A better approach would be to return a value that is invalid:

// The method to test in class Calculator ...
public int Sum(int x, int y)
{
   return 0;
}
Good Example: The test fails by returning an invalid result

In this case, the test will fail because the behavior is incorrect. It is not correctly adding the two numbers.
