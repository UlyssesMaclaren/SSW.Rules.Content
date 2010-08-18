---
type: rule
title: Do you use resource file for storing your static script?
uri: do-you-use-resource-file-for-storing-your-static-script
created: 2009-05-06T09:48:28.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 17
  title: Ryan Tee

---

 Write a Intro pragraph here<br> 
##  


```
StringBuilder sb = new StringBuilder();     sb.AppendLine(@"<script type=""text/javascript"">");     sb.AppendLine(@"function deleteOwnerRow(rowId)");     sb.AppendLine(@"{");     sb.AppendLine(string.Format(@"{0}.Delete({0}.        GetRowFromClientId(rowId));", OwnersGrid.ClientID));     sb.AppendLine(@"}");     sb.AppendLine(@"</script>");
```

Bad example - Hard to read ?the string is surrounded by rubbish + inefficient because you have an object and 6 strings



```
string.Format(@"<script type=""text/javascript"">                         function deleteOwnerRow(rowId)                          { {0}.Delete({0}.GetRowFromClientId(rowId)); } </script> ",        OwnersGrid.ClientID);
```

Good example Slightly easier to read ?but it is 1 code statement across 10 lines

```
string scriptTemplate = Resources.Scripts.DeleteJavascript;     string script = string.Format(scriptTemplate, OwnersGrid.ClientID);
```



```
<script type=""text/javascript"">     function deleteOwnerRow(rowId)     {            {0}.Delete({0}.GetRowFromClientId(rowId));     }     </script>
```


**Figure: The code in the first box, the string in the resource file in the 2nd box. This is the easiest to read + you can localize it eg. If you need to localize an Alert in the javascript**
![Create a Resource file](/Standards/SoftwareDevelopment/RulesToBetterDotNETProjects/PublishingImages/CreateResource_small.jpg) Figure: Add a recourse file into your project in VS2005![Create a Resource file](/Standards/SoftwareDevelopment/RulesToBetterDotNETProjects/PublishingImages/ReadResource_small.jpg) Figure: Read value from the new added resource file
