---
type: rule
title: Long Process - Do you show the status of progress bar on winform's title?
uri: long-process---do-you-show-the-status-of-progress-bar-on-winforms-title
created: 2012-11-27T02:59:56.0000000Z
authors: []

---

The importance of having the status of progress bar on winform's title:

- Users can clearly see the progress status.
- If the winform is minimized to taskbar, users still can see the progress status.

 
The form title should take the form of "[XX]% Completed - [Task Description] - [Product Name]".
There is another relevant rule about the [winform title](http://www.ssw.com.au/ssw/Standards/Rules/RulestoBetterInterfaces-Windows-Applications.aspx#TitleBarCaption).

[[badExample]]
| ![ Bad Example - The winform's title does not contain the progress status](../../assets/BadProgressForm.gif)

[[goodExample]]
| ![ Good Example - The winform's title contains the status of progress bar](../../assets/GoodProgressForm.gif)

![Winform's title with progress status (Taskbar)](../../assets/GoodProgressFormTaskbar.gif)Figure: Good Example - You can clearly see the progress status from taskbar when you have the windows minimized
![Winform's title with progress status (Taskbar)](../../assets/TaskBarProgress.png)Figure: Good Example - Windows 7 shows the progress in the taskbar (which is visible even when the application is minimized)
