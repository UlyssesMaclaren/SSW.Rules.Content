---
type: rule
title: Do you use "using" declaration instead of use explicitly "dispose"?
uri: do-you-use-using-declaration-instead-of-use-explicitly-dispose
created: 2018-04-26T20:56:47.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

Don't explicitly use "dispose" to close objects and dispose of them, the "using" statement will do all of them for you. It is another awesome tool that helps reduce coding effort and possible issues. 
​
 
static int WriteLinesToFile(IEnumerable&lt;string&gt; lines)
{
  // We must declare the variable outside of the using block
  // so that it is in scope to be returned.
  int skippedLines = 0;
  var file = new System.IO.StreamWriter("WriteLines2.txt")
  foreach (string line in lines)
  {
    if (!line.Contains("Second"))
    {
      file.WriteLine(line);
    }
    else
    {
      skippedLines++;
    }
  }
  file.Dispose();
  return skippedLines;
}
Figure: Bad example of dispose of resources



static int WriteLinesToFile(IEnumerable&lt;string&gt; lines)
{
  // We must declare the variable outside of the using block
  // so that it is in scope to be returned.
  int skippedLines = 0;
  using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
  {
    foreach (string line in lines)
    {
      if (!line.Contains("Second"))
      {
        file.WriteLine(line);
      }
      else
      {
        skippedLines++;
      }
    }
  } // file is disposed here
   return skippedLines;
}
Figure: Bad example of dispose of resources 

​

static int WriteLinesToFile(IEnumerable&lt;string&gt; lines)
{
  using var file = new System.IO.StreamWriter("WriteLines2.txt");
  // Notice how we declare skippedLines after the using statement.
  int skippedLines = 0;
  foreach (string line in lines)
  {
    if (!line.Contains("Second"))
    {
      file.WriteLine(line);
    }
    else
    {
      skippedLines++;
     }
    }
    // Notice how skippedLines is in scope here.
    return skippedLines;
   // file is disposed here
}​


Figure: Good example of dispose of resources, using c# 8.0 using declaration



TIP:​

**Did you know it is not recommended to dispose HttpClient?**

​​One last note is regarding disposing of HttpClient.  Yes, HTTPClient does implement IDisposable, however, I do not recommend creating a HttpClient inside a Using block to make a single request.  When HttpClient is disposed it causes the underlying connection to be closed also.  This means the next request has to re-open that connection.  You should try and re-use your HttpClient instances.  If the server really does not want you holding open it’s connection then it will send a header to request the connection be closed.​​
http://www.bizcoder.com/httpclient-it-lives-and-it-is-glorious​​​
