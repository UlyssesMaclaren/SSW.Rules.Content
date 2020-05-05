

---
authors:
  - id: 1
    title: Adam Cogan
---




<span class='intro'> If there are complex logic evaluations in your code, we recommend you isoloate them and write unit tests for them.<div>Take this for example&#58;<br></div> </span>

<p class="ssw15-rteElement-CodeArea">​while ((ActiveThreads &gt; 0 || AssociationsQueued &gt; 0) &amp;&amp; (IsRegistered || report.TotalTargets &lt;= 1000 )<br> &amp;&amp; (maxNumPagesToScan == -1 || report.TotalTargets &lt; maxNumPagesToScan) &amp;&amp; (!CancelScan)) </p><p>		</p><dd class="ssw15-rteElement-FigureNormal">Figure&#58; This complex logic evaluation can't be unit tested​<br></dd><p>Writing a unit test for this piece of logic is virtually impossible - the only time it is executed is during a scan, and there are lots of other things happening at the same time meaning the unit test will often fail and you won't be able to identify the cause anyway.</p><p>We can update this code to make it testable though.</p><p>Update the line to this&#58;</p><p class="ssw15-rteElement-CodeArea">while (!HasFinishedInitializing (ActiveThreads, AssociationsQueued, IsRegistered, <br> report.TotalTargets, maxNumPagesToScan, CancelScan))</p><p>		</p><dd class="ssw15-rteElement-FigureNormal">Figure&#58; Isolate the complex logic evaluation<br></dd><p>We are using all the same parameters - however now we are moving the actual logic to a separate method.</p><p>Now create the method&#58;</p><p class="ssw15-rteElement-CodeArea">private static&#160;bool HasFinishedInitializing(int ActiveThreads, int AssociationsQueued, bool IsRegistered, <br> int TotalAssociations, int MaxNumPagesToScan, bool CancelScan)<br>&#123;<br> return (ActiveThreads &gt; 0 || AssociationsQueued &gt; 0) &amp;&amp; (IsRegistered || TotalAssociations &lt;= 1000 )<br> &amp;&amp; (maxNumPagesToScan == -1 || TotalAssociations &lt; maxNumPagesToScan) &amp;&amp; (!CancelScan);		<br>&#125;</p><p>		</p><dd class="ssw15-rteElement-FigureNormal">Figure&#58; Function of the complex logic evaluation<br></dd><p>The critical thing is that everything the method needs to know is passed in, it mustn't go out and get any information for itself and mustn't rely on any other objects being instantiated. In Functional Programming this is called a &quot;Pure&#160;Function&quot;.&#160;A good way to enforce this is to make each of your logic methods static. It has to be completely self-contained.<br></p><p>The other thing we can do now is actually go and simplify / expand out the logic so that it's a bit easier to digest.</p><p class="ssw15-rteElement-CodeArea">private static&#160;bool HasFinishedInitializing(int ActiveThreads, int AssociationsQueued, bool IsRegistered, <br> int TotalAssociations, int MaxNumPagesToScan, bool CancelScan)<br>&#123;<br> //Cancel<br> if (CancelScan) <br> &#123; return true; &#125;<br> //only up to 1000 links if it is not a registered version<br> if (!IsRegistered &amp;&amp; TotalAssociations &gt; 1000) <br> &#123; return true; &#125;<br> //only scan up to the specified number of links<br> if (MaxNumPagesToScan != -1 &amp;&amp; TotalAssociations &gt; MaxNumPagesToScan) <br> &#123; return true; &#125;<br> //not ActiveThread and the Queue is full<br> if(ActiveThreads &lt;= 0 &amp;&amp; AssociationsQueued &lt;= 0) <br> &#123; return true; &#125;<br> return false;<br>&#125;		</p><dd class="ssw15-rteElement-FigureNormal">​Figure&#58; Simplify the complex logic evaluation<br></dd><p>The big advantage now is that we can unit test this code easily in a whole range of different scenarios!</p><p class="ssw15-rteElement-CodeArea">[Test]<br>public void HasFinishedInitializingLogicTest()<br>&#123;<br> Validator validator = new Validator();<br> //Set scenario A<br> int activeThreads = 2;<br> int associationsQueued = 20;<br> bool isRegistered = false;<br> int totalAssociations = 1200;<br> int maxNumPagesToScan = -1;<br> bool cancelScan = false;<br> bool actual = (bool)Reflection.InvokeMethod(&quot;HasFinishedInitializing&quot;, validator,<br> new object[] &#123;activeThreads, associationsQueued, isRegistered,<br> totalAssociations, maxNumPagesToScan, cancelScan&#125;);<br> Assert.IsTrue(actual, &quot;HasFinishedInitializing LogicTest A failed.&quot;);<br> //Set scenario B<br> activeThreads = 2;<br> associationsQueued = 20;<br> isRegistered = true;<br> totalAssociations = 1200;<br> maxNumPagesToScan = -1;<br> cancelScan = false;<br> actual = (bool)Reflection.InvokeMethod(&quot;HasFinishedInitializing&quot;, validator,<br> new object[] &#123;activeThreads, associationsQueued, isRegistered,<br> totalAssociations, maxNumPagesToScan, cancelScan&#125;);<br> Assert.IsFalse(actual, &quot;HasFinishedInitializing LogicTest B failed.&quot;);<br> &#125;	</p><p>		</p><dd class="ssw15-rteElement-FigureNormal">Figure&#58; Write a unit test for complex logic evaluation​<br></dd>

