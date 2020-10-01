---
type: rule
title: Do you use IntelliTesting to save you in testing?
uri: do-you-use-intellitesting-to-save-you-in-testing
created: 2020-03-12T23:35:41.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

It is difficult to measure test quality as there are a number of different available metrics - for example, code coverage and number of assertions. Furthermore, when we write code to test, there are a number of questions that we must answer, such as, "is the code easily testable?" and "are we only testing the happy path or have we included the edge cases?"

However, the most important question a dev can ask themselves is, "What assertions should I test?".

This is where IntelliTesting comes into play. The feature, formerly known as Smart Unit Testing (and even more formerly known as PEX), will help you answer this question by intelligently analyzing your code. Then, based on the information gathered, it will generate a unit test for each scenario it finds.
 [[badExample]]
| ![What’s wrong with this code?![IntelliTest-Good.png](IntelliTest-Good.png)](IntelliTest-bad.png)
In short, by using IntelliTest, you will increase code coverage, greatly increase the number of assertions tested, and increase the number of edge cases tested. By adding automation to your testing, you save yourself time in the long run and reduce the risk of problems in your code caused by simple human error.
