---
type: rule
title: Do you always create suggestions when something is hard to do?
uri: do-you-always-create-suggestions-when-something-is-hard-to-do
created: 2018-04-30T22:04:43.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

One of our goals is to make the job of the developer as easy as possible. If you have to write a lot of code for something that you think you should not have to do, you should make a suggestion and add it to the relevant page.

If you have to add a suggestion, make sure that you put the link to that suggestion into the comments of your code.
 
/// &lt;summary&gt;
/// base class for command implementations
/// This is a work around as standard MVVM commands
/// are not provided by default. 
/// &lt;/summary&gt;
public class Command : ICommand
{
 // code
}
Figure: Bad example - The link to the suggestion should be in the comments

/// &lt;summary&gt;
/// base class for command implementations
/// This is a work around as standard MVVM commands
/// are not provided by default. 
/// &lt;/summary&gt;
///
/// &lt;remarks&gt;
///  Issue Logged here: https://github.com/SSWConsulting/SSW.Rules/issues/3
///&lt;/remarks&gt;
public class Command : ICommand
{
 // code
}
Figure: Good example - When you link to a suggestion everyone can find it and vote it up
