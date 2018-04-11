---
# required metadata

title: Configure endpoint protection settings in Microsoft Intune - Azure | Microsoft Docs
description: Create endpoint protection settings when you create a macOS or Windows 10 device profile in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
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
# Add endpoint protection settings in Intune

Endpoint protection lets you control different security features on your devices, including firewall, bitlocker, allowing and blocking apps, Windows Defender and encryption, and more. You can configure these settings in Microsoft Intune using device profiles.

For example, you can create an endpoint protection profile that only allows macOS users to install apps from the Mac App Store. Or, enable Windows SmartScreen when running apps on Windows 10 devices.

This article shows you how to create a profile. Then, select your device platform for more details on the available settings.

## Create a device profile containing endpoint protection settings

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device configuration** > **Profiles** > **Create profile**.
4. Enter a **Name** and **Description** for the endpoint protection profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for device restriction settings:
   - **macOS**
   - **Windows 10 and later**
6. From the **Profile type** drop-down list, choose **Endpoint protection**. 
7. Depending on the platform you chose, the settings you can configure are different. Go to one of the following topics for detailed settings for each platform:
   - [macOS settings](endpoint-protection-macos.md)
   - [Windows 10 settings](endpoint-protection-windows-10.md)
8. When you're done, go back to the **Create profile** page, and click **Create**.

The profile is created and appears on the profiles list page. To assign this profile to groups, see [assign device profiles](device-profile-assign.md).

## Next steps
To assign a profile to groups, see [assign device profiles](device-profile-assign.md).
