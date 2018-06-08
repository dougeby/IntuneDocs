---
# required metadata

title: Create device profiles in Microsoft Intune - Azure | Microsoft Docs
description: Add or configure a device profile in Microsoft Intune, including selecting the platform type, and configuring the settings within the Azure portal.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/24/2018
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
ms.custom: intune-azure

---

# Create a device profile in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## Create the profile
1. In the [Azure portal](https://portal.azure.com), select **All Services**, and search for **Microsoft Intune**.

2. In **Microsoft Intune**, select **Device configuration**, and select **Profiles**. Then select **Create Profile**.

3. Enter the following properties:

   - **Name**: Enter a descriptive name for the new profile.
   - **Description**: Enter a description for the profile. (This is optional, but recommended.)
   - **Platform**: Select the platform type:  

       - **Android**
       - **Android for Work**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 and later**
       - **Windows 10 and later**

   - **Profile type**: Select the type you want to create. The list depends on the platform you choose.
   - **Settings**: The following topics describe the settings for each profile type:

       -  [Device features](device-features-configure.md)
       -  [Device restrictions](device-restrictions-configure.md)
       -  [Endpoint protection](endpoint-protection-configure.md)
       -  [Kiosk](kiosk-settings.md)
       -  [Email](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Education for [Windows 10](education-settings-configure.md) and [iOS](wi-fi-settings-ios.md)
       -  [Windows 10 edition upgrade](edition-upgrade-configure-windows-10.md)
       -  [iOS update policies](software-updates-ios.md)
       -  [Certificates](certificates-configure.md)
       -  [Windows Information Protection](windows-information-protection-configure.md)
       -  [Custom](custom-settings-configure.md)

     ![Screenshot of Create profile](./media/create-device-profile.png)

4. Select **Create** when finished.

The profile is created, and appears in the list.

## Next steps
[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
