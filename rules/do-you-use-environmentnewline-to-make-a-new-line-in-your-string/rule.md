---
type: rule
title: Do you use Environment.NewLine to make a new line in your string?
uri: do-you-use-environmentnewline-to-make-a-new-line-in-your-string
created: 2018-04-26T22:46:14.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 78
  title: Matt Wicks

---

When you need to create a new line in your string, make sure you use Environment.NewLine, and then literally begin typing your code on a new line for readability purposes.​
 
​string strExample = "This is a very long string that is \r\n not properly implementing a new line.";
 Bad Example: The string has implemented a manual carriage return line feed pair (\r\n)


string strExample = "This is a very long string that is " + Environment.NewLine +
			 " properly implementing a new line.";


OK Example: The new line is created with Enviroment.NewLine (but strings are immutable)

​var example = new StringBuilder();
 example.AppendLine("This is a very long string that is ");
 example.Append(" properly implementing a new line.");


Good Example: The new line is created by the StringBuilder and has better memory utilisation
