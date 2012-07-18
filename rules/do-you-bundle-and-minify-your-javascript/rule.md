---
type: rule
title: Do you bundle and minify your JavaScript?
uri: do-you-bundle-and-minify-your-javascript
created: 2012-07-18T17:35:19.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
Did you know you can improve the speed of your MVC app by using a built in feature called bundling and minification.
 
Bundling allows you to:

1. Specify the JavaScript files you want to include in your app and the order in which they are loaded
2. Put them into 1 JavaScript file reducing calls to the server.


The next part of the process is minification. This means that all the whitespace is removed from the JavaScript files and long variables names are shortened where possible to decrease the size of the package.
 All this adds up to a faster MVC app and a better user experience.

Layout.cshtml
<br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
 <br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
 <br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
  <br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
 <br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
 <br>&lt;script type="text/javascript" src="/SoftwareDevelopment/RulesToBetterMVC/Pages/@Url.Content("&gt;&lt;/script&gt;
 Figure: Scripts are specified in the view
BundleConfig.cs
<br>public static void RegisterBundles(BundleCollection bundles)
 <br>        {
 <br>            bundles.Add(new ScriptBundle("~/bundles/SSW").Include(
 <br>                        "~/Scripts/2011.3.1115/jquery-1.6.4.min.js", 
 <br>                        "~/Scripts/jquery-ui-1.8.16.min.js",
 <br>                        "~/Scripts/jquery.formatCurrency-1.4.0.min.js",
 <br>                        "~/Scripts/date.js",
 <br>                        "~/Scripts/jquery.watermark.min.js",
 <br>                        "~/Scripts/jquery.cross-slide.min.js"));
 <br>        }

Layout.cshtml
<br>@Scripts.Render("~/bundles/ssw")Figure: A bundle is created in the bundle config and then referenced in the view
