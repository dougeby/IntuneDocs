---
# required metadata

title: Set enrollment restrictions in Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Restrict enrollment by platform and set a device enrollment limit in Intune. "
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
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
#ms.custom:
---

# Set enrollment restrictions 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You can set the types and maximum number of devices that you will allow to enroll. On the Enrollment Restrictions blade, you can set:

- The platforms that are allowed to enroll, and whether to block enrollment of personally owned devices for Android and iOS.

- The maximum number of devices that a user is allowed to enroll.

## Set device type restrictions

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Enrollment Restrictions**.

3. Under **Device Type Restrictions**, select **Default**.

4. On the **All Users** blade, select **Platforms**.

5. For platforms that are allowed to enroll in Intune, select **Allow**. For platforms that you want to block from enrolling, select **Block**. Platforms are set to **Allow** by default. 

    >[!NOTE]
    >These settings do not apply to or block Windows enrollments that use the Intune software client. These settings affect only enrollment using mobile device management. 

6. Select **Save**.

7. Select **Platform Configurations**.

8. Choose whether to **Allow** or **Block** personally owned iOS and Android devices from enrolling.

9. Select **Save**.

## Set device limit restrictions

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Enrollment Restrictions**.

3. Under **Device Limit Restrictions**, select **Default**.

4. On the **All Users** blade, select **Device Limit**.

5. Select the maximum number of devices that a user can enroll, and then select **Save**.
