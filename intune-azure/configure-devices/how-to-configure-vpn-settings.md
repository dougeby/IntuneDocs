---
# required metadata

title: How to configure Microsoft Intune VPN settings | Intune Azure preview | Microsoft Docs
description: Learn how to use Intune to configure VPN connections on devices you manage.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure VPN settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Virtual private networks (VPNs) give your users secure remote access to your company network. Devices use a VPN connection profile to initiate a connection with the VPN server. Use **VPN profiles** in Microsoft Intune to deploy VPN settings to users and devices in your organization, so they can easily and securely connect to the network.

For example, assume that you want to provision all iOS devices with the settings required to connect to a file share on the corporate network. You create a VPN profile that contains the settings necessary to connect to the corporate network, and then you assign this profile to all users who have iOS devices. The users will see the VPN connection in the list of available networks and can connect with minimal effort.

## Create a device profile containing VPN settings

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings. Currently, you can choose one of the following platforms for VPN device settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **VPN**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](vpn-for-android.md)
	- [iOS settings](vpn-for-ios.md)
	- [macOS settings](vpn-for-macos.md)
	- [Windows Phone 8.1 settings](vpn-for-windows-phone-8-1.md)
	- [Windows 8.1 settings](vpn-for-windows-8-1.md)
	- [Windows 10 settings](vpn-for-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

