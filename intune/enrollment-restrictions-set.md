---
# required metadata

title: Set enrollment restrictions in Intune
titleSuffix: "Intune on Azure"
description: Restrict enrollment by platform and set a device enrollment limit in Intune. "
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
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

As an Intune admin, you can determine which devices can enroll into management with Intune. Use the Intune portal to set the following restrictions for device enrollment:

- Maximum number of enrolled devices
- Device platforms that can enroll:
  - Android
  - iOS
  - macOS
  - Windows
- Restrict personally owned devices (iOS, Android, macOS only)

>[!NOTE]
>Enrollment restrictions are not a security feature. Compromised devices can misrepresent their operating system information. These restrictions are a best-effort barrier for non-malicious users.

## Set default enrollment restrictions
The default enrollment restrictions apply to all users who aren't assigned higher priority enrollment restrictions.  
1. In the Intune portal, choose **Device enrollment**, choose **Enrollment restrictions**.
![Screenshot of the device restrictions workspace with the default device type restrictions and device limit restrictions.](media/device-restrictions-set-default.png)
2. Under **Enrollment restrictions** > **Device Type Restrictions**, select **Default**.
3. Under **All Users**, select **Platforms**. Choose **Allow** or **Block** for each platform:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Click **Save**.
4. Under **All Users**, select **Platform Configurations** and select the following configurations:
  - **Personally Owned** - Specify whether to **Allow** or **Block** for Android, iOS, and macOS devices.
  ![Screenshot of the device restrictions workspace with the default device platform configurations showing personally owned settings configured.](media/device-restrictions-platform-configurations.png)
  Click **Save**.

## Create new enrollment restrictions

1. In the Intune portal, choose **Device enrollment**, choose **Enrollment restrictions**, and then choose **Create**.
![Screenshot of the device restrictions workspace with the Create button highlighted.](media/device-restrictions-create.png)
2. Specify the **Name** and **Description** of the enrollment restriction for administrative purposes. These settings do not display to end users.
3. Select the **Restriction Type** to create:
  - **Device Type Restriction** - Specify platform restrictions:
    - Device platforms that can enroll:
      - Android
      - iOS
      - macOS
      - Windows
    - Restrict personally owned devices (iOS, Android, macOS only)
  - **Device Limit Restrictions** - Specify the maximum number of enrolled devices per user
4. Click **Create** to create the new enrollment restriction.
5. Select **Groups Assigned** to assign these enrollment restrictions to groups of users, and then select **Assign**.
6. Assign this restriction to groups of users. You can multi-select groups with the **Ctrl** key. Choose **Select** to save your selections, and then **Assign** to apply the enrollment restrictions to groups.
![Screenshot of device enrollment restrictions showing priority and properties for enrollment restrictions.](media/device-restrictions-create-list.png)
7. You can adjust the priority of enrollment restrictions by dragging and dropping the enrollment restrictions up or down.
