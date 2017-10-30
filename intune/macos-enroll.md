---
# required metadata

title: Enroll macOS devices in Intune
titlesuffix: "Azure portal"
description: Learn how to enroll macOS devices in Intune."
keywords:
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
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

# Enroll macOS devices in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune enables you to manage macOS devices. To enable device management, your users must enroll their devices by going to the [Company Portal website](http://portal.manage.microsoft.com), and following the prompts. Once macOS devices are under management, you can [create custom settings for macOS devices](custom-settings-macos.md). More capabilities are coming soon.

## Prerequisites

Complete the following prerequisites before setting up macOS device enrollment:

- [Configure domains](custom-domain-name-configure.md)
- [Set the MDM Authority](mdm-authority-set.md)
- [Create groups](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configure the Company Portal](company-portal-app.md)
- Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Get an Apple MDM push certificate](apple-mdm-push-certificate-get.md)

## Set up macOS enrollment

By default, Intune already allows enrollment of macOS devices.

To block macOS devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).

## Tell your users how to enroll their devices to access company resources

You'll need to tell your end users to go to the [Company Portal website](http://portal.manage.microsoft.com), and follow the prompts to enroll their devices. You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](end-user-educate.md)
- [Using your iOS or macOS device with Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
