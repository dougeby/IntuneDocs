---
# required metadata

title: How to import Wi-Fi settings for Windows 8.1 and later devices with Microsoft Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Import Wi-Fi settings from Windows into an Intune Wi-Fi profile."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to import Wi-Fi settings for Windows 8.1 and later devices with Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

For devices that run Windows 8.1 or Windows 10 desktop or mobile, you can import a Wi-Fi configuration profile that was previously exported to a file. 

## To export Wi-Fi settings from a Windows device

In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune. On a Windows computer that already has the required WiFi profile installed, follow this following procedure.
1. Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.
1. Open up a Command Prompt as an administrator.
1. Run the command **netsh wlan show profiles**, and note the name of the profile you'd like to export. In this example, the profile name is **WiFiName**.
1. Run this command: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**.This will create a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.

## To import the Wi-Fi settings into Intune

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.
5. From the **Platform** drop-down list, choose **Windows 8.1 and later**.
6. From the **Profile** type drop-down list, choose **Wi-Fi import**.
7. On the **Wi-Fi Basic** blade, configure the following:
	- **Connection name** Enter the name of the Wi-Fi connection. This name will be displayed to end users when they browse available Wi-Fi networks.
	- **Profile XML** Click the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.
	- **File contents** Displays the XML code for the configuration profile you selected.
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

