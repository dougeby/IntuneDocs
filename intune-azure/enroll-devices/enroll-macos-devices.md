---
# required metadata

title: Enroll macOS devices in Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to enroll macOS devices in Intune Azure preview."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
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
#ms.custom:

---

# Enroll macOS devices in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As an Intune administrator, you can manage macOS devices. By default, the Azure portal allows users to enroll their macOS devices. You just need to tell your users to go to the [Company Portal website](http://portal.manage.microsoft.com) and enroll their macOS device. 

## Prerequisites

Complete the following prerequisites before setting up macOS device enrollment:

- [Configure domains](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Set the MDM Authority](set-mdm-authority.md)
- [Create groups](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configure the Company Portal](/intune-azure/manage-apps/company-portal-app.md)
- Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Get an Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)

## Set up macOS enrollment

By default, Intune is already set up to allow enrollment of macOS devices. 

To see the setting to allow or block macOS devices from enrollment, go to the Intune blade in the Azure portal, and choose **Enrollment** > **Enrollment Restrictions**. 

## Tell your users how to enroll their devices to access company resources

For end-user enrollment instructions, see [Enroll your macOS device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Using your iOS or macOS device with Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)