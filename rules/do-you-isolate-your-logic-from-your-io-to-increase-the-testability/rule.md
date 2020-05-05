

---
authors:
  - id: 1
    title: Adam Cogan
---




<span class='intro'> If your method is consists of logic and IO, we recommend you isolate them to increase the testability of the logic.<div>Take this for example (and see how we refactor it)&#58;<br></div> </span>

<p class="ssw15-rteElement-CodeArea">public static List&lt;string&gt; GetFilesInProject(string projectFile)<br>&#123;<br> List&lt;string&gt; files = new List&lt;string&gt;();<br> TextReader tr = File.OpenText(projectFile);<br> Regex regex = RegexPool.DefaultInstance[RegularExpression.GetFilesInProject];<br> MatchCollection matches = regex.Matches(tr.ReadToEnd());<br> tr.Close();<br> string folder = Path.GetDirectoryName(projectFile);<br> foreach (Match match in matches)<br> &#123;<br> string filePath = Path.Combine(folder, match.Groups[&quot;FileName&quot;].Value);<br> if (File.Exists(filePath))<br> &#123;<br> files.Add(filePath);<br> &#125;<br> &#125;<br> return files;<br>&#125;</p><dd class="ssw15-rteElement-FigureBad">Bad - The logic and the IO are coded in a same method<br></dd><p>While this is a small concise and fairly robust piece of code, it still isn't that easy to unit test. Writing a unit test for this would require us to create temporary files on the hard drive, and probably end up requiring more code than the method itself.</p><p>If we start by refactoring it with an overload, we can remove the IO dependency and extract the logic further making it easier to test&#58;</p><p class="ssw15-rteElement-CodeArea">public static List&lt;string&gt; GetFilesInProject(string projectFile)<br>&#123;<br> string projectFileContents;<br> using (TextReader reader = File.OpenText(projectFile))<br> &#123;<br> projectFileContents = reader.ReadToEnd();<br> reader.Close();<br> &#125;<br> string baseFolder = Path.GetDirectoryName(projectFile);<br> return GetFilesInProjectByContents(projectFileContents, baseFolder, true);<br>&#125;<br>public static List&lt;string&gt; GetFilesInProjectByContents(string projectFileContents, string baseFolder, bool checkFileExists)<br>&#123;<br> List&lt;string&gt; files = new List&lt;string&gt;();<br> Regex regex = RegexPool.DefaultInstance[RegularExpression.GetFilesInProject];<br> MatchCollection matches = regex.Matches(projectFileContents);<br> foreach (Match match in matches)<br> &#123;<br> string filePath = Path.Combine(baseFolder, match.Groups[&quot;FileName&quot;].Value);<br> if (File.Exists(filePath) || !checkFileExists)<br> &#123;<br> files.Add(filePath);<br> &#125;<br> &#125;<br> return files;<br>&#125;</p><dd class="ssw15-rteElement-FigureGood">Good - The logic is now isolated from the IO<br></dd><p>The first method (GetFilesInProject) is simple enough that it can remain untested. We do however want to test the second method (GetFilesInProjectByContents). Testing the second method is now too easy&#58;</p><p class="ssw15-rteElement-CodeArea">[Test]<br>public void TestVS2003CSProj()<br>&#123;<br> string projectFileContents = VSProjects.VS2003CSProj;<br> string baseFolder = @&quot;C&#58;\NoSuchFolder&quot;;<br> List&lt;string&gt; result = CommHelper.GetFilesInProjectByContents(projectFileContents, baseFolder, false);<br> Assert.AreEqual(15, result.Count);<br> Assert.AreEqual(true, result.Contains(Path.Combine(baseFolder, &quot;BaseForm.cs&quot;)));<br> Assert.AreEqual(true, result.Contains(Path.Combine(baseFolder, &quot;AssemblyInfo.cs&quot;)));<br>&#125;<br>[Test]<br>public void TestVS2005CSProj()<br>&#123;<br> string projectFileContents = VSProjects.VS2005CSProj;<br> string baseFolder = @&quot;C&#58;\NoSuchFolder&quot;;<br> List&lt;string&gt; result = CommHelper.GetFilesInProjectByContents(projectFileContents, baseFolder, false);<br> Assert.AreEqual(6, result.Count);<br> Assert.AreEqual(true, result.Contains(Path.Combine(baseFolder, &quot;OptionsUI.cs&quot;)));<br> Assert.AreEqual(true, result.Contains(Path.Combine(baseFolder, &quot;VSAddInMain.cs&quot;)));<br>&#125;</p><dd class="ssw15-rteElement-FigureGood">Good - Different test cases and assertions are created to test the logic​<br></dd>

