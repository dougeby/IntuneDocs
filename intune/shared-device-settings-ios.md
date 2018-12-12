---
# required metadata

title: Customize lock screen on iOS devices using Microsoft Intune - Azure | Microsoft Docs
titlesuffix:
description: Learn the Microsoft Intune settings you can use to display information on the iOS device lock screen using shared device configuration settings for iOS.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Shared device configuration settings to display messages on the iOS device lock screen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

This article shows you the Microsoft Intune settings you can use to show information on the iOS device lock screen.

Use these settings to show a custom message or text on the sign-in window and lock screen. For example, you can enter an "If lost, return to ..." message and asset tag information.

These settings support supervised devices running iOS 9.3 and later.

## Create the profile

1. In the [Azure Portal](https://portal.azure.com), select **All services** > filter on **Intune** > select **Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter a **Name** and **Description** for the profile.
4. In **Platform**, select **iOS**. In **Profile type**, select **Device features**.
5. In **Settings**, select **Lock Screen Message (supervised only)**. Configure the following settings:

    - **Asset tag information**: Enter information about the asset tag of the device. For example, enter `Owned by Contoso Corp`.

        The text you enter is shown on the sign-in window and lock screen on the device.

    - **Lock screen footnote**: If the device is lost or stolen, enter a note that might help get the device returned. For example, enter something like `If found, call Contoso at ...`.

    Variables can also be used for these settings. For example, to show the serial number, enter `Serial Number {{serialNumber}}`. On the lock screen, the text shows similar to `Serial Number 123456789ABC`. When entering variables, be sure to use curly brackets `{{ }}`. [App configuration tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) includes a list of variables that can be used. You can also use `deviceName` or any other device-specific value.

6. When finished, select **OK** > **OK** > **Create**. Your profile is shown in the list.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
