---
type: rule
title: Do you know how to setup a Boot to VHD Image?
uri: do-you-know-how-to-setup-a-boot-to-vhd-image
created: 2011-04-13T05:26:11.0000000Z
authors:
- id: 21
  title: Matthew Hodgkins

---

Using Boot to VHD is very similar to dual-booting your machine, except that you do not have to partition your hard drive. It also has performance benefits over using a Hyper-V server for presentations. <br> **Pre-Requisites** 


- The presentation computer running Window 7
- A SysPreped VHD image to be deployed onto the presentation computer


1. Copy a SysPreped VHD image to the laptop to be used for the presentation.
2. Open an Administrative command prompt.
3. Type:
bcdedit /copy {default} /d “Demo-NameOfDemo”
![Creating the entry using BCDEdit shows your GUID](fig1-creatingentry.png)
4. Type:
bcdedit /set **device** vhd=[D:]\VM-DEV-SharePoint\_2010\_Public\_Beta.vhd
**D:\** is the drive the VHD is located and  **VM-DEV-SharePoint\_2010\_Public\_Beta.vhd** is the location of your VHD file. Make sure you replace   with the GUID you got in the previous step.
5. Type:
bcdedit /set **osdevice** vhd=[D:]\VM-DEV-SharePoint\_2010\_Public\_Beta.vhd
**D:\** is the drive the VHD is located and  **VM-DEV-SharePoint\_2010\_Public\_Beta.vhd** is the location of your VHD file. Make sure you replace   with the GUID you got in the previous step.
6. Type:
bcdedit /set  detecthal on
![Each time you run a BCDEdit command it should return "The operation completed successfully"](fig2-addguids.png)
7. Reboot the computer and now you will have the option to choose between Windows 7 and the new Boot to VHD image.
