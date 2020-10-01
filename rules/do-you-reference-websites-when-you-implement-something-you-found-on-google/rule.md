---
type: rule
title: Do you reference websites when you implement something you found on Google?
uri: do-you-reference-websites-when-you-implement-something-you-found-on-google
created: 2018-04-26T22:18:56.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

If you end up using someone else's code, or even idea, that you found online, make sure you add a reference to this in your source code. There is a good chance that you or your team will revisit the website. And of course, it never hurts to tip your hat off to other coders.

 
private void HideToSystemTray()
{
 // Hide the windows form in the system tray
 if (FormWindowState.Minimized == WindowState)
 { 
 Hide();
 } 
}
Bad Example: The website where the solution was found IS NOT referenced in the comments


private void HideToSystemTray()
{
 // Hide the windows form in the system tray
 // I found this solution at http://www.developer.com/net/csharp/article.php/3336751
 if (FormWindowState.Minimized == WindowState)
 { 
 Hide();
 } 
}
Good Example: The website where the solution was found is referenced in the comments
