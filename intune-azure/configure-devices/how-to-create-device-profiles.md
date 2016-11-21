---
# required metadata

title: How to create Microsoft Intune device configuration profiles| Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to create Microsoft Intune device configuration profiles

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. In the **Device Configuration** workload, choose **Profiles**.
2. On the blade showing the list of profiles, choose **Create Profile**.
3. On the **Create Profile** blade, specify the following:
	- **Name** - Enter a descriptive name for the new profile.
	- **Description** -  Enter an optional description for the profile.
	- **Platform** -  Select the platform type for the profile you want to create.
	- **Profile type** - Select the type of profile you want to create. The list of available types will differ depending on the platform you chose.
	- **Settings** - See the following topics for information about the settings for each profile type:
		-  [Device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions)
		-  [Email settings](/intune-azure/configure-devices/how-to-configure-email-settings)
		-  [VPN settings](/intune-azure/configure-devices/how-to-configure-vpn-settings)
		-  [Wi-Fi settings](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
		-  [Windows 10 edition upgrade settings](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
		-  [Certificate settings](/intune-azure/configure-devices/how-to-configure-certificates)
		-  [Windows Information Protection settings](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
		-  [Education settings](/intune-azure/configure-devices/education-settings-for-ios.md)
		-  [Custom settings](/intune-azure/configure-devices/how-to-configure-custom-settings)
4. Once you are done configuring settings, on the **Create Profile** blade, choose **Create**.

The new profile is created on the list of profiles blade.

For information about how to assign device profiles, see [How to assign device profiles with Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).

