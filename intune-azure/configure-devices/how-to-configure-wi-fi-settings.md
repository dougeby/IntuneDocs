---
# required metadata

title: How to configure Microsoft Intune Wi-Fi settings | Intune Azure preview | Microsoft Docs
description: Learn how to use Intune to configure Wi-Fi connections on devices you manage.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure Wi-Fi settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use Microsoft Intune Wi-Fi profiles to deploy wireless network settings to users and devices in your organization. When you deploy a Wi-Fi profile, your users will have access to your corporate Wi-Fi network without having to configure it themselves.

For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network. Here's the process:

1. Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.
2. Assign the profile to a group containing all users of iOS devices.
3. Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.

Wi-Fi profiles support the following device platforms:

- Android 4 and later
- iOS 8.0 and later
- macOS (Mac OS X 10.9 and later)

For devices running Windows 8.1, Windows 10, and Windows 10 Mobile, you can import a Wi-Fi configuration that was previously exported from another device.

Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing Wi-Fi settings

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings. Currently, you can choose one of the following platforms for Wi-Fi settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows 8.1 and later (import a profile)**
6. From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.
	>[!TIP]
	>Use **Wi-fi basic** to supply basic features like the network name, and the SSID. **Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this. **Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previusly exported from a different device.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](wi-fi-for-android.md)
	- [iOS settings](wi-fi-for-ios.md)
	- [macOS settings](wi-fi-for-macos.md)
	- [Windows Phone 8.1 settings](wi-fi-import-for-windows-8-1.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

