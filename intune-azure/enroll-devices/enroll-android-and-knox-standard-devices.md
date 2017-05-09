---
# required metadata

title: Enroll Android devices in IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to enroll Android devices in Intune Azure preview."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/12/2017
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
ms.custom: intune-azure

---

# Enroll Android devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune enables you to manage Android devices, including Samsung Knox Standard devices. To enable device management, your users must enroll their devices by downloading the Intune Company Portal app, which is available from Google Play, and then opening the app and following the prompts to enroll. Once Android devices are under management, you can [create compliance policies](../set-device-compliance/create-a-compliance-policy-for-android.md), [manage apps](../manage-apps/what-is-app-management.md), and more.

Devices that run Samsung KNOX Standard, are now supported for multi-user management by Intune. This means that end users can sign in and out of the device with their Azure AD credentials, the device is centrally managed whether it’s in use or not. When end users sign-in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.

## Prerequisite

You must set the MDM authority to **Microsoft Intune** to prepare to manage mobile devices. See [Set the MDM authority](set-mdm-authority.md) for instructions. You set this item only once, when you are first setting up Intune for mobile device management, so you may have already set this.

## Set up Android enrollment

By default, Intune already allows enrollment of Android and Samsung Knox Standard devices.

To block Android devices, or to block only personally owned Android devices from enrollment, see [Set device type restrictions](det-enrollment-restrictions.md#set-device-type-restrictions).

To set the maximum number of devices that a user can enroll, see [Set device limit restrictions](set-enrollment-restrictions.md#set-device-limit-restrictions).

## Tell your users how to enroll their devices to access company resources

You'll need to tell your end users to go to Google Play to download the Intune Company Portal app, and then open the app and follow the prompts to enroll their device. The app guides users through the enrollment process, explaining what users can expect and what IT administrators can and can't see on their devices.

You can also send them a link to online enrollment steps: [Enroll your Android device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android).

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Using your Android device with Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
