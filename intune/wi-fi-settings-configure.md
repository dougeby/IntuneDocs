---
# required metadata

title: How to configure Intune Wi-Fi settings
titleSuffix: Microsoft Intune
description: Learn how to use Microsoft Intune to configure Wi-Fi connections on devices you manage.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Wi-Fi settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization. When you assign a Wi-Fi profile, your users have access to your corporate Wi-Fi network without having to configure it themselves.

For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network. Here's the process:

1. Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.
2. Assign the profile to a group containing all users of iOS devices.
3. Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.

## Supported device platforms

Wi-Fi profiles support the following device platforms:

- Android 4 and later
- Android for Work
- iOS 8.0 and later
- macOS (Mac OS X 10.9 and later)

For devices running Windows 8.1, Windows 10, Windows 10 Mobile, and Windows Holographic for Business, you can import a Wi-Fi configuration that was previously exported from another device.

Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing Wi-Fi settings

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
2. On the **Device configuration** pane under the **Manage** section, choose **Profiles**.
3. On the profiles pane, choose **Create profile**.
4. On the **Create profile** pane, enter a **Name** and **Description** for the Wi-Fi profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings. Currently, you can choose one of the following platforms for Wi-Fi settings:
	- **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**

   > [!IMPORTANT]
   > If you are creating a profile for devices running Windows 10, including Windows Holographic for Business, you must choose the **Windows 8.1 and later** platform. The **Windows 10 and later** platform doesn't include a Wi-Fi profile type. 

6. For Apple or Android devices, on the **WiFi type** drop-down list, choose **Basic** or **Enterprise**. You can use **Basic** to supply basic features like the network name, and the SSID. **Enterprise** lets you supply more advanced information like the Extensible Authentication Protocol (EAP), if your Wi-Fi network uses this protocol. 

   The **Wi-Fi import** profile (for Windows 8.1 and later) lets you import Wi-Fi settings as an XML file that you previously exported from a different device.
1. Depending on the platform you chose, the settings you can configure is different. Go to one of the following topics for detailed settings for each platform:
	- [Android and Android for Work settings](wi-fi-settings-android.md)
	- [iOS settings](wi-fi-settings-ios.md)
	- [macOS settings](wi-fi-settings-macos.md)
	- [Windows 8.1 and later settings](wi-fi-settings-import-windows-8-1.md) (including Windows Holographic for Business)
1. When you're done, go back to the **Create Profile** pane, and hit **Create**.

The profile is created and appears on the profiles list pane.

## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
