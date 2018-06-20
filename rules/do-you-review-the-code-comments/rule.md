---
type: rule
title: Do you review the code comments?
uri: do-you-review-the-code-comments
created: 2012-04-01T09:31:34.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 23
  title: Damian Brady

---

 
Comments can be useful for documenting code but should be used properly. Some developers like seeing lots of code comments and some don't.
 
Some tips for including comments in your code are:

1. Comments aren't always the solution.  Sometimes it's better to refactor the comments into the actual method name. If your method needs a comment to tell a developer what it does, then the method name is probably not very clear.
2. Comments should never say **\*what\*** the code does, it should say **\*why\*** the code does it.  Any decent developer can work out what a piece of code does.
3. Comments can also be useful when code is missing.  For example, why there is no locking code around a thread-unsafe method.


// returns the Id of the first customer with the matching last name
public int GetResult(string lastname)
{
    // get the first matching customer from the repository
    return repository.Customer.First(c =&gt; c.LastName.StartsWith(lastname));
} Figure: Bad Example - The first comment is only valuable because the method is poorly named, while the second describes \*what\* is happening, not \*why\*.public int GetFirstCustomerWithLastName(string lastname)
{
    // we use StartsWith because the legacy system sometimes padded with spaces
    return repository.Customer.First(c =&gt; c.LastName.StartsWith(lastname));
}Figure: Good Example - The method has been renamed so no comment is required, and the comment explains \*why\* the code has been written in that way.

Good code is so nice it doesn't need comments, but when it does:

- Includes comments that explain the intent (the "why" rather than the "what")

public Customer GetFirstCustomerWithLastName(string lastName)
{
  // we use StartsWith because the legacy system sometimes padded with spaces
  return \_repository.Customer.FirstOrDefault(c =&gt; c.LastName.StartsWith(lastName));
} Figure: Good comments explain the intent of the code rather than what it is doing
