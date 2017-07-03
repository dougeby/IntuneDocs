---
# required metadata

title: Intune shared device configuration settings for iOS
titleSuffix: "Intune on Azure"
description: Learn the Intune settings you can use to display information on the iOS device lock screen."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Shared Device configuration settings to display messages on the iOS device lock screen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Shared device configuration settings let you specify optional text displayed on the login window and lock screen. For example, you can enter an "If Lost, Return to" message and Asset Tag Information. 

>[!IMPORTANT]
> This capability is supported on supervised devices running iOS 9.3 and later.

1. On the **Device features** blade, choose **Shared Device Configuration (supervised only)**.
2. On the **Shared Device Configuration (supervised only)** blade, configure the following settings:
	- **Asset tag information** - Enter information about the asset tag of the device. For example: **Owned by Contoso Corp**.
	The information you enter is applied to all devices you assign this profile to.
	- **Lock screen footnote** - If the device is lost or stolen, enter a note that might help get the device returned. For example: **If found, call 'number'**.
3. When you are finished, choose **OK** until you return to the **Create Profile** blade, then choose **Create**. 


## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).