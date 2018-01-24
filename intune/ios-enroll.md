---
# required metadata

title: Choose how to enroll Windows devices in Intune
titlesuffix: "Azure portal"
description: Learn how to set up enrollment of Windows devices in Microsoft Intune."
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll iOS devices in Intune

Intune enables mobile device management (MDM) of iPads and iPhones to give users access to company email and apps.

As an Intune admin, you can enable enrollment for iOS devices. You can allow users to enroll personally owned devices, known as "bring your own device" (BYOD) enrollment. You can also enable enrollment of company-owned devices.

## Prerequisites for iOS enrollment
Before you can enable iOS devices, complete the following steps:
- [Set up Intune](setup-steps.md) - These steps set up your Intune infrastructure. In particular, device enrollment requires that you [set your MDM authority](mdm-authority-set.md).
- [Get an Apple MDM Push certificate](apple-mdm-push-certificate-get.md) - Apple requires a certificate to enable management of iOS and macOS devices.

## User-owned iOS devices (BYOD)

You can let users enroll their personal devices for Intune management, know as "bring your own device" or BYOD. Once you've completed the prerequisites and assigned users licenses, they can download the iOS Company Portal app from the App Store, and follow enrollment instructions in the app.

## Company-owned iOS devices
For organizations that purchase devices for their users, Intune supports the following iOS company-owned device enrollment methods:

- Apple's Device Enrollment Program (DEP)
- Apple School Manager
- Apple Configurator Setup Assistant enrollment
- Apple Configurator direct enrollment

You can also enroll company-owned iOS devices with a [device enrollment manager](device-enrollment-manager-enroll.md) account.

## Device Enrollment Program
Organizations can purchase iOS devices through Apple's Device Enrollment Program (DEP). DEP lets you deploy an enrollment profile “over the air” to bring devices into management. Learn more about [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## Apple School Manager
Apple School Manager is a device purchase and enrollment program for schools. Like DEP, you can deploy a profile to enroll devices in management. Learn more about [Apple School Manager](apple-school-manager-set-up-ios.md).

## Apple Configurator
You can enroll iOS devices with Apple Configurator running on a Mac computer. To prepare devices, you USB-connect them and install an enrollment profile. You can enroll devices with Apple Configurator in two ways:
- Setup Assistant enrollment - Factory resets the device, prepares it to run Setup Assistant, and installs the company's policies for the device’s new user.
- Direct enrollment - Does not factory-reset the device and enrolls the device with a predefined policy. This method is for devices with no user affinity.

Learn more about [Apple Configurator enrollment](apple-configurator-setup-assistant-enroll-ios.md).
