---
type: rule
title: Printers - Do You Install Your Printers With Group Policy?
uri: printers---do-you-install-your-printers-with-group-policy
created: 2012-03-05T15:03:34.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 It is important install your printers automatically to all clients that logon to the domain. 
This can be achieved via Group Policy. This can be setup easily on a Microsoft Windows 2008 Server R2:

- From Server Manager add the Print Services role
![Install the Print Services role](/ITAndNetworking/RulesToBetterWindowsServers/PublishingImages/install-print-roles.jpg)Figure: Install the Print Services role- When the role has installed, open Print Management from Administrative Tools
- Install all your printers by right clicking on Printers and clicking Add Printer
![Add all of your printers to the server](/ITAndNetworking/RulesToBetterWindowsServers/PublishingImages/add-printers.jpg)Figure: Add all of your printers to the server- Right click on Drivers and choose Add Drivers. From here you will be able to install the x86 and x64 drivers for your printers so all workstations in your organization get the printer drives automatically
![Add the additional drivers for both x86 and x64](/ITAndNetworking/RulesToBetterWindowsServers/PublishingImages/add-drivers.jpg)Figure: Add the additional drivers for both x86 and x64- Click on Printers in the menu to get a list of your installed printers
- Right click on the first printer you want to install via group policy and click on Deploy with Group Policy
![Deploying your printer with Group Policy](/ITAndNetworking/RulesToBetterWindowsServers/PublishingImages/deploy-printer.jpg)Figure: Deploying your printer with Group Policy- Next you need to choose a Group Policy Object (GPO) to add the printers to. You may wish to create a new GPO specifically for the printers, which you can do through the Group Policy Management tool in Administrative Tools
![Select the Group Policy Object (GPO) to add the printers to](/ITAndNetworking/RulesToBetterWindowsServers/PublishingImages/select-gpo.jpg)Figure: Select the Group Policy Object (GPO) to add the printers to- Repeat the last 2 steps for each printer you want to add automatically using Group Policy
- Reboot your workstations and the new printers will be added upon logon


