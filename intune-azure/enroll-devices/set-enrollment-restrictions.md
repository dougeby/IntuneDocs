---
# required metadata

title: Set enrollment restrictions in Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Restrict enrollment by platform and set a device enrollment limit in Intune. "
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
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

# Set enrollment restrictions in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You can limit the types of devices that are allowed to enroll in Intune by specifying the allowable platforms. You can also set the maximum number of devices that a user is allowed to enroll.

## Set device type restrictions

1. In the **Enrollment** blade, choose **Enrollment Restrictions**.

2. Under **Device Type Restrictions**, select **Default**.

3. On the **All Users** blade, select **Platforms**.

4. For platforms that are allowed to enroll in Intune, select **Allow**. For platforms that you want to block from enrolling, select **Block**.

5. Select **Save**.

6. Select **Platform Configurations**.

7. Choose whether to Allow or Block personally owned iOS devices from enrolling.

8. Select **Save**.

## Set device limit restrictions

1. In the **Enrollment** blade, choose **Enrollment Restrictions**.

2. Under **Device Limit Restrictions**, select **Default**.

3. On the **All Users** blade, select **Device Limit**.

4. Select the maximum number of devices that a user can enroll, and then select **Save**.
