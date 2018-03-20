---
# required metadata

title: Set up enrollment for macOS devices
titlesuffix: Microsoft Intune
description: Learn how to set up enrollment for macOS devices in Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
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

# Set up enrollment for macOS devices in Intune

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

## User-owned iOS devices (BYOD)

You can let users enroll their personal devices for Intune management, know as "bring your own device" or BYOD. Once you've completed the prerequisites and assigned users licenses, they can download the macOS Company Portal app from the App Store, and follow enrollment instructions in the app.

## Company-owned iOS devices
For organizations that purchase devices for their users, Intune supports enrolling company-owned macOS devices with a [device enrollment manager](device-enrollment-manager-enroll.md) account.

## Set up macOS enrollment

By default, Intune already allows enrollment of macOS devices.

To block macOS devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).

## Tell your users how to enroll their devices to access company resources

Tell your end users to go to the [Company Portal website](https://portal.manage.microsoft.com) and follow the prompts to enroll their devices. You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

For information about other end-user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](end-user-educate.md)
- [Using your macOS device with Intune](/intune-user-help/using-your-macos-device-with-intune)

## Enroll virtual macOS machines for testing

> [!NOTE]
> macOS virtual machines are only supported for testing. You should not use macOS virtual machines as production devices for your end users. 

You can enroll macOS virtual machines for testing using either Parallels Desktop or VMware Fusion. 

For Parallels Desktop, you need to set the hardware type and the serial number for the virtual machines so that Intune can recognize them. Follow Parallels' instructions for [setting hardware type](http://kb.parallels.com/123594) and [serial number](http://kb.parallels.com/123455) to set up the necessary settings for testing. We recommend that you match the hardware type of the device running the virtual machines to the hardware type of the virtual machines that you're creating. You can find this hardware type in **Apple menu** > **About this Mac** > **System Report** > **Model Identifier**. 

For VMware Fusion, you need to [edit the .vmx file](https://kb.vmware.com/s/article/1014782) to set the virtual machine's hardware model and serial number. We recommend that you match the hardware type of the device running the virtual machines to the hardware type of the virtual machines that you're creating. You can find this hardware type in **Apple menu** > **About this Mac** > **System Report** > **Model Identifier**. 
