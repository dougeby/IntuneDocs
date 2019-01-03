---
# required metadata

title: Windows Holographic Business shared device settings - Microsoft Intune - Azure | Microsoft Docs
description: Add and use Windows Holographic for Business to configure devices that are shared, or used by multiple users in Microsoft Intune. See a list of all the settings and what they do on the devices, including Microsoft HoloLens. Control guest accounts, manage accounts and delete inactive accounts, allow or prevent saving to local storage, set power and sleep options, choose when updates are installed, and use devices in education environments in a device configuration profile.
keywords:
author: MandiOhlinger

ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; seodec18

---

# Windows Holographic for Business settings to manage shared devices using Intune

Windows Holographic for Business devices, such as the Microsoft HoloLens, can be used by multiple users. Devices that have multiple users are called shared devices, and are a part of mobile device management (MDM) solutions. 

Using Microsoft Intune, users can sign in to these shared devices with a guest account. As they use the device, they only get access to features you allow. For example, you choose if the device goes in to sleep mode, if users can see and save files locally, and more.

When the user signs off, these credentials are cached. You can also control if the guest account deletes when the user signs off, or delete inactive accounts when a threshold is reached.

This article lists and describes the settings you use in a Windows Holographic for Business device configuration profile. When the profile is created in Intune, you can then deploy or assign the profile to device groups in your organization. You can also assign this profile to a device group with mixed device types and OS versions.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All Services** > filter on **Intune** > select **Intune**.
2. Select **Device configuration** > **Profiles** > **Create Profile**.
3. Enter the following properties:

   - **Name**: Enter a descriptive name for the new profile.
   - **Description**: Enter a description for the profile. This setting is optional, but recommended.
   - **Platform**: Select **Windows 10 and later**.
   - **Profile type**: Select **Shared multi-user device**.

Next, enter the settings to configure this profile for your environment.

## Shared multi-user device settings

- **Shared PC mode**: Choose **Enable** to turn on shared PC mode. In this mode, only one user signs in to the device at a time. Another user can't sign in until the first user signs out. **Not configured** (default) leaves this setting unmanaged by Intune, and doesn't push any policy to control this setting on a device.
- **Guest account**: Choose to create a Guest option on the sign-in screen. Guest accounts don't require any user credentials or authentication. This setting creates a new local account each time it's used. Your options:
  - Guest: Creates a guest account locally on the device.
  - Domain: Creates a guest account in Azure Active Directory (AD).
  - Guest and domain: Creates a guest account locally on the device, and in Azure Active Directory (AD).
- **Account management**: Set to **Enable** to automatically delete local accounts created by guests, and accounts in AD and Azure AD. When a user signs off the device, or when system maintenance runs, these accounts are deleted. When enabled, also set:
  - **Account Deletion**: Choose when accounts are deleted: **At storage space threshold**, **At storage space threshold and inactive threshold**, or **Immediately after log-out**. Also enter:
    - **Start delete threshold(%)**: Enter a percentage (0-100) of disk space. When the total disk/storage space drops below the value you enter, the cached accounts are deleted. It continuously deletes accounts to reclaim disk space. Accounts that are inactive the longest are deleted first.
    - **Stop delete threshold(%)**: Enter a percentage (0-100) of disk space. When the total disk/storage space meets the value you enter, the deleting stops.

  Set to **Disable** to keep the local, AD, and Azure AD accounts created by guests.

  > [!NOTE]
  > Microsoft HoloLens devices only support the **Account management** settings.

- **Local Storage**: Choose **Enabled** to prevent users from saving and viewing files on the device's hard drive. Choose **Disabled** to allow users to see and save files locally using File Explorer. **Not configured** (default) leaves this setting unmanaged by Intune, and doesn't push any policy to control this setting on a device.
- **Power Policies**: When set to **Enabled**, users can't turn off hibernate, can't override all sleep actions (such as closing the lid), and can't change the power settings. When set to **Disabled**, users can hibernate the device, can close the lid to sleep the device, and change the power settings. **Not configured** (default) leaves this setting unmanaged by Intune, and doesn't push any policy to control this setting on a device.
- **Sleep time out (in seconds)**: Enter the number of inactive seconds (0-100) before the device goes into sleep mode. If you don't set a time, the device goes to sleep after 60 minutes.
- **Sign-in when PC wakes**: Set to **Enabled** to require the user to sign in with a password when device comes out of sleep mode. Choose **Disabled** so users don't have to enter their username and password. **Not configured** (default) leaves this setting unmanaged by Intune, and doesn't push any policy to control this setting on a device.
- **Maintenance start time(in minutes from midnight)**: Enter the time in minutes (0-1440) when automatic maintenance tasks, such as Windows Update, run. The default start time is midnight, or zero (`0`) minutes. Change the start time by entering a start time in minutes from midnight. For example, if you want maintenance to begin at 2 AM, enter `120`. If you want maintenance to begin at 8 PM, enter `1200`.
- **Education policies**: Choose **Enabled** to use the recommended settings for devices used in schools, which are more restrictive. Choose **Disabled** so the default and recommended education policies aren't used. **Not configured** (default) leaves this setting unmanaged by Intune, and doesn't push any policy to control this setting on a device.

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).