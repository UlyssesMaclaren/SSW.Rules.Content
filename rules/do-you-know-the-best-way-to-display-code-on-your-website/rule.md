---
type: rule
title: Do you know the best way to display code on your website?
uri: do-you-know-the-best-way-to-display-code-on-your-website
created: 2016-08-05T18:57:08.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

Any website designer that needs to display code should be aware that there is a very simple method for simply formatting code, and there is a slow and complex method.

The complex method requires formatting each line with HTML tags (such as &lt;br&gt; and &nbsp;) to ensure the code looks nice and pretty.

The simpler method uses &lt;pre&gt; tags. Pre (standing for "preformatted") means that the code is formatted exactly as it is written in the HTML window. This means the page designer can format code in a very simple fashion, without worrying about tags.​
 
​​**Note:** &lt;code&gt; tags should not be used because they only provide the font Courier - you still have to manually indent all of your code as in the bad code display example below.

&lt;font face="Courier, Times, Arial, Verdana" size="3"&gt;
public class Configuration&lt;br&gt;
&nbsp;{&lt;br&gt;
&nbsp;&nbsp;public static string MySetting&lt;br&gt;
&nbsp;&nbsp;{&lt;br&gt;
&nbsp;&nbsp;&nbsp;get&lt;br&gt;
&nbsp;&nbsp;&nbsp;{&lt;br&gt;
&lt;/font&gt;
 Figure: Bad code display example - using &lt;font&gt; 
&lt;code&gt;
public class Configuration&lt;br&gt;
&nbsp;{&lt;br&gt;
&nbsp;&nbsp;public static string MySetting&lt;br&gt;
&nbsp;&nbsp;{&lt;br&gt;
&nbsp;&nbsp;&nbsp;get&lt;br&gt;
&nbsp;&nbsp;&nbsp;{&lt;br&gt;
&lt;/code&gt;
 Figure: Bad code display example - using &lt;code&gt;
&lt;pre&gt;
public class Configuration
{
public static string MySetting
{
get
{
&lt;/pre&gt;
 Figure: Good code display example - using &lt;pre&gt;

**Tip:** Do not use auto-format (Ctrl-K, Ctrl-F) in Visual Studio when updating page with &lt;pre&gt; tags, or it will destroy all the code formatting. We have made a suggestion to Microsoft to fix this.
