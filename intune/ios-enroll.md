---
# required metadata

title: Choose how to enroll Windows devices in Intune
titleSuffix: "Intune on Azure"
description: Learn how to set up enrollment of Windows devices in Microsoft Intune."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
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

After these prerequisites are complete, users can install the Company Portal app to enroll their personal iOS devices, or the admin can set up corporate-owned iOS device management. Admins can also assign [device enrollment managers](device-enrollment-manager-enroll.md) who can enroll many devices with a single management account. Intune supports the following iOS company-owned device enrollment methods:

## Device Enrollment Program
Organizations can purchase iOS devices through Apple's Device Enrollment Program (DEP). DEP lets you deploy an enrollment profile “over the air” to bring devices into management. Learn more about [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## Apple School Manager
Apple School Manager is a device purchase and enrollment program for schools. Like DEP, you can deploy a profile to enroll devices in management. Learn more about [Apple School Manager](apple-school-manager-set-up-ios.md).

## Apple Configurator
You can enroll iOS devices with Apple Configurator running on a Mac computer. To prepare devices, you USB-connect them and install an enrollment profile. You can enroll devices with Apple Configurator in two ways:
- Setup Assistant enrollment - Factory resets the device, prepares it to run Setup Assistant, and installs the company's policies for the device’s new user.
- Direct enrollment - Does not factory-reset the device and enrolls the device with a predefined policy. This method is for devices with no user affinity.

Learn more about [Apple Configurator enrollment](apple-configurator-setup-assistant-enroll-ios.md).
