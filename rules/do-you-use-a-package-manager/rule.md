---
type: rule
title: Do you use a package manager?
uri: do-you-use-a-package-manager
created: 2016-06-17T06:29:18.0000000Z
authors:
- id: 47
  title: Stanley Sidik

---

A package manager is a collection of software tools that automate the process of installing, upgrading, configuring, and uninstalling computer programs in a consistent manner. [Chocolatey](https://chocolatey.org/) is a great package manager, easy to use way to manage software on Windows. 
  ![chocolatey.png](chocolatey.png) 

To get started with Chocolatey open up Command Prompt in Administrative mode, type in:


```
@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
```


Alternatively, [install Chocolatey via their website](https://chocolatey.org/install).

To find a list of software that we use, along with a PowerShell script to run, check out our [Intranet](https://intranet.ssw.com.au/SysAdmin/Lists/WinImageInstalledSoftware/AllItems.aspx) page.

Alternatives: Homebrew on a Mac
