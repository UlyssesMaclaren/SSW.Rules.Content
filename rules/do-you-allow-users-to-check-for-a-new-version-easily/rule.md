---
type: rule
title: Do you allow users to check for a new version easily?
uri: do-you-allow-users-to-check-for-a-new-version-easily
created: 2009-02-28T09:42:15.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

It is important to give users the ability to check for a new version of the application they are using. And once located it should be easily downloaded and installed. You need:

1. A visual identifier such as a tick or a cross on the main menu
2. A "Check for Updates" option in our Help menu.


Remember:

- This is mainly for Windows Forms, but you can do the same for new versions of Web Applications - e.g. a knowledge base package or Reporting Services Application.
- You can do a complete check of your PC at the click of a button using [SSW Diagnostics](http://www.ssw.com.au/ssw/Diagnostics/Default.aspx).
- Since this check occurs over the web, you should use [threading](http://www.ssw.com.au/ssw/Standards/Rules/RulesToBetterWindowsForms.aspx#GuiThreading) to avoid slowing down the forms responsiveness. This is a generic component that is available in the [SSW .NET Toolkit](http://www.ssw.com.au/ssw/NETToolkit/Default.aspx).
- If the UI is a Windows Service, be aware that they don't open up the UI very often. Therefore you can't rely on this method. In a coming release Diagnostics will ask for your email and let you know when updates are available for you PC.


![BAD UI - a nagging message box that forces the User to click OK](MSN.gif)

![Show a Tick when the application is up to date](GoodUI.gif)

![Show a Cross when the application is out of date](BadUI.gif)

To keep the consistent look and consistent code, we have implemented our version checker as a user control.

![SSW.Framework.WindowsUI.VersionStatus](VersionStatusControl.gif)
As it is a user control, we can easily implement this in all our applications. We just need to place the user control on the winform, and have the ProductDownloadID and ProductLatestVersionURL entered with the correct values.

![Enter the ProductDownloadID and ProductLatestVersionURL](VersionStatusProperties.gif)

![Include 'Check for Updates' in your applications](CheckForUpdate.gif)
