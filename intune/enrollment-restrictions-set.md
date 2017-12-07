---
# required metadata

title: Set enrollment restrictions in Intune
titlesuffix: "Azure portal"
description: Restrict enrollment by platform and set a device enrollment limit in Intune. "
keywords:
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2

# optional metadata

#ROBOTS: 
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Set enrollment restrictions

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As an Intune administrator, you can create and manage enrollment restrictions which define the number and types of devices that can enroll into management with Intune. You can create multiple restrictions and apply them to different user groups. You can set the [priority order](#change-enrollment-restriction-priority) for your different restrictions.

>[!NOTE]
>Enrollment restrictions are not security features. Compromised devices can misrepresent their character. These restrictions are a best-effort barrier for non-malicious users. 

The specific enrollment restrictions that you can create include:

- Maximum number of enrolled devices
- Device platforms that can enroll:
  - Android
  - Android for Work
  - iOS
  - macOS
  - Windows
- Platform operating system version for iOS, Android, Android for Work, and Windows (only Windows 10 versions may be used, leave this blank if Windows 8.1 is allowed)
  - Minimum version
  - Maximum version
- Restrict personally owned devices (iOS, Android, Android for Work, macOS only)

## Default restrictions

Default restrictions are automatically provided for both device type and device limit enrollment restrictions. You can change the options for the defaults. Default restrictions apply to all user and userless enrollments. You can override these defaults by creating new restrictions with higher priorities.

## Create a restriction

1. Sign into the Azure portal.
2. Choose **More Services**, search for **Intune**, and then choose **Intune**.
3. Choose **Device enrollment** > **Enrollment restrictions**.
4. Choose **Create restriction**.
5. Give the restriction a name and description.
6. Choose a **Restriction type** and then click **Create**.
7. For device limit restrictions, click **Device limit** to set the maximum number of devices that a user can enroll.
8. For device type restrictions, click **Platforms** and **Platform configurations** to allow or block various platforms and versions.
9. Click **Assignments** > **+ Select groups**.
10. Under **Select groups**, select one or more groups, and then click **Select**. The restriction only applies to groups to which it is assigned. If you don't assign a restriction to at least one group, it won't have any effect.
11. Click **Save**.
12. The new restriction is created with a priority just above the default. You can [change the priority](#change-enrollment-restriction-priority).

## Set device type restrictions

You can change the settings for a device type restriction by following these steps:

1. Sign into the Azure portal.
2. Choose **More Services**, search for **Intune**, and then choose **Intune**.
3. Choose **Device enrollment** > **Enrollment restrictions**.
4. Under **Device Type Restrictions**, choose the restriction that you want to set.
5. Under the restriction name (**All Users** for the default restriction), select **Platforms**. Choose **Allow** or **Block** for each platform listed.
6. Click **Save**.
7. Under the restriction name (**All Users** for the default restriction), select **Platform Configurations** and select the minimum and maximum **Versions** for the platforms listed. Supported versions include:
  - Android and Android for Work support major.minor.rev.build.
  - iOS supports major.minor.rev.
  - Windows supports major.minor.rev.build for Windows 10 only.
  Operating system versions don't apply to Apple devices enrolling with Device Enrollment Program, Apple School Manager, or the Apple Configurator app. 
8. Specify whether to **Allow** or **Block** **Personally owned** devices for each platform listed.

    ![Screenshot of the device restrictions workspace with the default device platform configurations showing personally owned settings configured.](media/device-restrictions-platform-configurations.png)
9. Click **Save**.

>[!NOTE]
>- If you block personally owned Android devices from enrollment, personally owned Android for Work devices can still enroll.
>- By default, your Android for Work devices settings will be the same as your settings for your Android devices. However, after you change your Android for Work settings that will no longer be the case.
>- If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.

## Set device limit restrictions

You can change the settings for a device limit restriction by following these steps:

1. Sign into the Azure portal.
2. Choose **More Services**, search for **Intune**, and then choose **Intune**.
3. Choose **Device enrollment** > **Enrollment restrictions**.
4. Under **Device Limit Restrictions**, choose the restriction that you want to set.
5. Choose **Device Limit** and then, in the drop-down list, select the maximum number of devices a user can enroll.
    ![Screenshot of the device limit restrictions blade with the device limit restrictions.](./media/device-restrictions-limit.png)
6. Click **Save**.

## Change enrollment restriction priority

Priority is used when a user exists in multiple groups that are assigned restrictions. Users are subject only to the highest priority restriction assigned to a group that they are in. For example, Joe is in a group A assigned to priority 5 restrictions and group B assigned to priority 2 restrictions. Joe is only subject to the priority 2 restrictions. 

When you create a restriction, it is added to the list just above the default.

Device enrollment includes default restrictions for both device type and device limit restrictions. These two restrictions apply to all users unless they are overridden by higher-priority restrictions. 

You can change the priority of any non-default restriction. 

**To change restriction priority**

1. Sign into the Azure portal.
2. Choose **More Services**, search for **Intune**, and then choose **Intune**.
3. Choose **Device enrollment** > **Enrollment restrictions**.
4. Hover over the restriction in the priority list.
5. Using the three vertical dots, drag the priority to the desired position in the list.





