---
# required metadata

title: Enroll Android devices in Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to enroll Android devices in Intune Azure preview."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll Android devices in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As an Intune administrator, you can enable management of Android devices, including Samsung Knox Standard devices, from the Company Portal. Users can then enroll their devices using the Company Portal app that is available from Google Play.

## Prerequisite

You must set the MDM authority to **Microsoft Intune** to prepare to manage mobile devices. See [Set the MDM authority](set-mdm-authority.md) for instructions. You set this item only once, when you are first setting up Intune for mobile device management, so you may have already set this. 

## Set up Android enrollment

By default, Intune is set up to allow enrollment of Android and Samsung Knox Standard devices. 

To see the setting to allow or block Android devices from enrollment, go to the Intune blade in the Azure portal, and choose **Enrollment** > **Enrollment Restrictions**. 

## Tell your users how to enroll their devices to access company resources

For end-user enrollment instructions, see [Enroll your Android device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Using your Android device with Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)