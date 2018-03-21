---
# required metadata

title: Microsoft Intune shared device configuration settings for iOS
titlesuffix:
description: Learn the Microsoft Intune settings you can use to display information on the iOS device lock screen.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
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

# Shared device configuration settings to display messages on the iOS device lock screen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This article shows you the Microsoft Intune settings you can use to display information on the iOS device lock screen.

Shared device configuration settings let you specify optional text displayed on the login window and lock screen. For example, you can enter an "If Lost, Return to" message and Asset Tag Information. 

>[!IMPORTANT]
> This capability is supported on supervised devices running iOS 9.3 and later.

## Create shared device settings

1. From [Intune in the Azure Portal](https://portal.azure.com), navigate to [**Device features** in the device configuration area](device-features-configure.md). 
1. On the **Device features** pane, choose **Shared Device Configuration (supervised only)**.
2. On the **Shared Device Configuration (supervised only)** pane, configure the following settings:
	- **Asset tag information** - Enter information about the asset tag of the device. For example: **Owned by Contoso Corp**.
	The information you enter is applied to all devices you assign this profile to.
	- **Lock screen footnote** - If the device is lost or stolen, enter a note that might help get the device returned. For example: **If found, call 'number'**.
3. When you are finished, choose **OK** until you return to the **Create profile** pane, then choose **Create**. 


## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).
