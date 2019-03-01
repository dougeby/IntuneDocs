---
# required metadata

title: macOS device settings in Microsoft Intune - Azure | Microsoft Docs
titlesuffix:
description: Add, configure, or create settings on macOS devices to restrict features, including setting password requirements, control the locked screen, use built-in apps, add restricted or approved apps, handle bluetooth devices, connect to the cloud for back up and storage, enable kiosk mode, add domains, and control how users interact with the Safari web browser in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: conceptual
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
ms.collection: M365-identity-device-management
---

# macOS device settings to allow or restrict features using Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

This article lists and describes the different settings you can control on macOS devices. As part of your mobile device management (MDM) solution, use these settings to allow or disable features, set password rules, allow or restrict specific apps, and more.

These settings are added to a device configuration profile in Intune, and then assigned or deployed to your macOS devices.

## Before you begin

[Create a device restrictions configuration profile](device-restrictions-configure.md#create-the-profile).

## General

- **Block content caching**: Choose **Not configured** (default) to enable content caching. Content caching stores app data, web browser data, downloads, and more locally on the device. Select **Block** to prevent this data from being stored in the cache.

  For more information on content caching on macOS, see [Manage content caching on Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (opens another website).

  This feature applies to:  
  - macOS 10.13 and later

- **Defer software updates (supervised only)**: When set to **Not configured** (default), software updates are shown on the device as Apple releases them. For example, if a macOS update gets released by Apple on a specific date, then that update naturally shows up on the device around the release date.

  **Enable** allows you to delay when software updates are shown on devices, from 0-90 days. This setting doesn't control when updates are or aren't installed. 

  - **Delay visibility of software updates**: Enter a value from 0-90 days. When the delay expires, users get a notification to update to the earliest version of the OS available when the delay was triggered.

    For example, if a macOS update is available on **January 1**, and **Delay visibility** is set to **5 days**, then the update isn't shown as an available update on devices. On the **sixth day** following the release, that update is available, and end users can install it.

    This feature applies to:  
    - macOS 10.13.4 and later

## Password

- **Password**: Require the end user to enter a password to access the device.
  - **Required password type**: Specify whether the password can be Numeric only, or whether it must be Alphanumeric (contain letters and numbers). This setting is supported only on Mac OS X version 10.10.3 and later.
  - **Number of non-alphanumeric characters in password**: Specify the number of complex characters required in the password (**0** to **4**).<br>A complex character is a symbol, for example "**?**".
  - **Minimum password length**: Enter the minimum length of password a user must configure (between **4** and **16** characters).
  - **Simple passwords**: Allow the use of simple passwords such as **0000** or **1234**.
  - **Maximum minutes after screen lock before password is required**: Specify how long the computer must be inactive before a password is required to unlock it.
  - **Maximum minutes of inactivity until screen locks**: Specify the length of time that the computer must be idle before the screen locks.
  - **Password expiration (days)**: Specify how many days elapse before the user must change the password (**1** to **255** days).
  - **Prevent reuse of previous passwords**: Enter the number of previously used passwords that can't be reused, from **1** to **24**.

- **Block password AutoFill**: Choose **Block** to prevent using the AutoFill Passwords feature on macOS. Choosing **Block** also has the following impact:

  - Users aren't prompted to use a saved password in Safari or in any apps.
  - Automatic Strong Passwords are disabled, and strong passwords aren't suggested to users.

  **Not configured** allows these features.

- **Block password proximity requests**: Choose **Block** so a user’s device doesn't request passwords from nearby devices. **Not configured** allows these password requests.

- **Block password sharing**: **Block** prevents sharing passwords between devices using AirDrop. **Not configured** allows passwords to be shared.

## Restricted apps

In the restricted apps list, you can configure one of the following lists:

- A **Prohibited apps** list: List the apps not managed by Intune that users aren't allowed to install and run. Users aren't prevented from installing a prohibited app, but if they do, it's reported to the administrator.
- An **Approved apps** list: List the apps that users are allowed to install. Users must not install apps that aren't listed. Apps that are managed by Intune are automatically allowed. Users aren't prevented from installing an app that isn't on the approved list. But, if they do, it's reported to the administrator.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the bundle ID of the app (for example *com.apple.calculator*).

## Domains

### Unmarked email domains

In the **Email Domain URL** field, add one or more URLs to the list. When users receive an email from a domain other than one you configured, the email is marked as untrusted in the MacOS Mail app.

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

You can also restrict device features and settings on [iOS](device-restrictions-ios.md) devices.