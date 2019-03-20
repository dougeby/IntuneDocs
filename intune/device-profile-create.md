---
# required metadata

title: Create device profiles in Microsoft Intune - Azure | Microsoft Docs
description: Add or configure a device configuration profile in Microsoft Intune. Select the platform type, configure the settings, and add a scope tag.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Create a device profile in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Devices profiles allow you to add and configure settings, and then push these settings to devices in your organization. [Apply features and settings on your devices using device profiles](device-profiles.md) goes into more detail, including what you can do.

This article:

- Lists the steps to create a profile.
- Shows you how to add a scope tag to "filter" the profile.
- Lists the check-in refresh cycle times when devices receive profiles and any profile updates.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All Services** > filter on **Intune** > select **Intune**.

2. Select **Device configuration**. You have the following options:

    - **Overview**: Lists the status of your profiles, and provides additional details on the profiles you assigned to users and devices.
    - **Manage**: Create device profiles, upload custom [PowerShell scripts](intune-management-extension.md) to run within the profile, and add data plans to devices using [eSIM](esim-device-configuration.md).
    - **Monitor**: Check the status of a profile for success or failure, and also view logs on your profiles.
    - **Setup**: Add a SCEP or PFX certificate authority, or enable [Telecom Expense Management](telecom-expenses-monitor.md) in the profile.

3. Select **Profiles** > **Create Profile**. Enter the following properties:

   - **Name**: Enter a descriptive name for the profile.
   - **Description**: Enter a description for the profile. This setting is optional, but recommended.
   - **Platform**: Choose the platform of your devices. Your options:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 and later**
       - **Windows 10 and later**

   - **Profile type**: Select the type of settings you want to create. The list shown depends on the **platform** you choose.
   - **Settings**: The following articles describe the settings for each profile type:

       - [Administrative templates](administrative-templates-windows.md)
       - [Custom](custom-settings-configure.md)
       - [Delivery optimization](delivery-optimization-windows.md)
       - [Device features](device-features-configure.md)
       - [Device restrictions](device-restrictions-configure.md)
       - [Edition upgrade and mode switch](edition-upgrade-configure-windows-10.md)
       - [Education](education-settings-configure.md)
       - [Email](email-settings-configure.md)
       - [Endpoint protection](endpoint-protection-configure.md)
       - [Identity protection](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [PKCS certificate](certficates-pfx-configure.md)
       - [SCEP certificate](certificates-scep-configure.md)
       - [Trusted certificate](certificates-configure.md)
       - [Update policies](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     For example, if you select **iOS** for the platform, your profile type options look similar to the following profile:

     ![Create iOS profile in Intune](./media/create-device-profile.png)

4. When finished, select **OK** > **Create** to save your changes. The profile is created, and shown in the list.

## Scope tags

After you add the settings, you can also add a scope tag to the profile. Scope tags assign and filter policies to specific groups, such as HR or All US-NC employees.

For more information about scope tags, and what you can do, see [Use RBAC and scope tags for distributed IT](scope-tags.md).

### Add a scope tag

1. Select **Scope (Tags)**.
2. Select **Add** to create a new scope tag. Or, select an existing scope tag from the list.
3. Select **OK** to save your changes.

## Refresh cycle times

Intune uses the following refresh cycles to check for updates to configuration profiles:

| Platform | Refresh cycle|
| --- | --- |
| iOS | Every 6 hours |
| macOS | Every 6 hours |
| Android | Every 8 hours |
| Windows 10 PCs enrolled as devices | Every 8 hours |
| Windows Phone | Every 8 hours |
| Windows 8.1 | Every 8 hours |

If the device recently enrolled, the check-in runs more frequently:

| Platform | Frequency |
| --- | --- |
| iOS | Every 15 minutes for 6 hours, and then every 6 hours |  
| macOS | Every 15 minutes for 6 hours, and then every 6 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows 10 PCs enrolled as devices | Every 3 minutes for 30 minutes, and then every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 

At any time, users can open the Company Portal app, and sync the device to immediately check for profile updates.

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
