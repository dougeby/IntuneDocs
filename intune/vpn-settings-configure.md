---
# required metadata

title: How to configure Intune VPN settings
titleSuffix: "Azure portal"
description: Learn how to use Intune to configure VPN connections on devices you manage."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure VPN settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Virtual private networks (VPNs) give your users secure remote access to your company network. Devices use a VPN connection profile to initiate a connection with the VPN server. Use **VPN profiles** in Microsoft Intune to assign VPN settings to users and devices in your organization, so they can easily and securely connect to the network.

For example, assume that you want to provision all iOS devices with the settings required to connect to a file share on the corporate network. You create a VPN profile that contains the settings necessary to connect to the corporate network, and then you assign this profile to all users who have iOS devices. The users will see the VPN connection in the list of available networks and can connect with minimal effort.

## VPN connection types

You can create VPN profiles using the following connection types:

|Connection type|Android<br>Android for Work|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Pulse Secure|Yes|Yes|Yes|Yes|Yes|Yes|
|Cisco (IPSec)|No|Yes|No|No|No|No|
|Citrix|Yes|Yes|No|No|No|Yes|
|F5 Edge Client|Yes|Yes|Yes|Yes|Yes|Yes|
|Dell SonicWALL Mobile Connect|Yes|Yes|Yes|Yes|Yes|Yes|
|Check Point Capsule VPN|Yes|Yes|Yes|Yes|Yes|Yes|
|Cisco AnyConnect|Yes|Yes|Yes|No|No|No|
|Automatic|No|No|No|No|No|Yes|
|IKEv2|No|No|No|No|No|Yes|
|L2TP|No|No|No|No|No|Yes|
|PPTP|No|No|No|No|No|Yes|
|Custom|No|Yes|Yes|No|No|No|


> [!IMPORTANT]
> Before you can use VPN profiles assigned to a device, you must install the applicable VPN app for the profile. You can use the information in the [What is app management in Microsoft Intune?](app-management.md) topic to help you assign the app by using Intune.  

Learn how to  create custom VPN profiles by using URI settings in [Create custom VPN profiles](custom-vpn-profiles-create.md).     

## Create a device profile containing VPN settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings. Currently, you can choose one of the following platforms for VPN device settings:
	- **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **VPN**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android and Android for Work settings](vpn-settings-android.md)
	- [iOS settings](vpn-settings-ios.md)
	- [macOS settings](vpn-settings-macos.md)
	- [Windows Phone 8.1 settings](vpn-settings-windows-phone-8-1.md)
	- [Windows 8.1 settings](vpn-settings-windows-8-1.md)
	- [Windows 10 settings](vpn-settings-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).


## Methods of securing VPN profiles

VPN profiles can use a number of different connection types and protocols from different manufacturers. These connections are typically secured through one of two methods.

### Certificates

When you create the VPN profile, you choose a SCEP or PKCS certificate profile that you previously created in Intune. This is known as the identity certificate. It's used to authenticate against a trusted certificate profile (or *root certificate*) that you created to establish that the user’s device is allowed to connect. The trusted certificate is assigned to the computer that authenticates the VPN connection, typically, the VPN server.

For more information about how to create and use certificate profiles in Intune, see [How to configure certificates with Microsoft Intune](certificates-configure.md).

### User name and password

The user authenticates to the VPN server by providing a user name and password.
