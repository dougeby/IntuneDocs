---
# required metadata

title: Enroll macOS devices in IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to enroll macOS devices in Intune Azure preview."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll macOS devices in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune enables you to manage macOS devices. To enable device management, your users must enroll their devices by going to the [Company Portal website](http://portal.manage.microsoft.com), and following the prompts. Once macOS devices are under management, you can [create custom settings for macOS devices](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-macos). More capabilities are coming soon.

## Prerequisites

Complete the following prerequisites before setting up macOS device enrollment:

- [Configure domains](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Set the MDM Authority](set-mdm-authority.md)
- [Create groups](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configure the Company Portal](/intune-azure/manage-apps/company-portal-app.md)
- Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Get an Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)

## Set up macOS enrollment

By default, Intune already allows enrollment of macOS devices. 

To block macOS devices from enrollment, see [Set device type restrictions](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions). 

To set the maximum number of devices that a user can enroll, see [Set device limit restrictions](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## Tell your users how to enroll their devices to access company resources

You'll need to tell your end users to go to the [Company Portal website](http://portal.manage.microsoft.com), and follow the prompts to enroll their devices. You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). 

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Using your iOS or macOS device with Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)