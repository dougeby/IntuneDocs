---
# required metadata

title: Choose how to enroll Windows devices in Intune
titlesuffix: "Azure portal"
description: Learn how to set up enrollment of Windows devices in Microsoft Intune."
keywords:
author: ErikjeMS
ms.author: erikje
manager: angrobe
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

## Use the Company Portal on DEP-enrolled or Apple Configurator-enrolled devices

Devices that are configured with user affinity can install and run the Company Portal app to download apps and manage devices. After users receive their devices, they must complete a number of additional steps to complete the Setup Assistant and install the Company Portal app.

User affinity is required to support the following:
  - Mobile application management (MAM) apps
  -	Conditional access to email and company data
  -	Company Portal app

**How users enroll corporate-owned iOS devices with user affinity**
1. When users turn on their device, they are prompted to complete the Setup Assistant. During setup, users are prompted for their credentials. They must use the credentials (i.e. the unique personal name or UPN) that are associated with their subscription in Intune.

2. During setup, users are prompted for an Apple ID. They must provide an Apple ID to allow the device to install the Company Portal. They can also provide the ID from the iOS settings menu after setup is finished.

3. After completing setup, the iOS device must install the Company Portal app from the App Store.

4. The user can now sign in to the Company Portal by using the UPN that they used when setting up the device.

5. After logging in, the user is prompted to enroll their device. The first step is to identify their device. The app presents a list of iOS devices that have already been corporate enrolled and assigned to the user’s Intune account. They should choose the matching device.

  If this device is not already corporate enrolled, they should choose **new device** to continue with the standard enrollment flow.

6. On the next screen, the user must confirm the serial number of the new device. The user can tap the link **confirm the Serial Number** which will launch instructions to use the Settings app to verify the serial number. The user must then enter the last four characters of the serial number into the Company Portal app.

  This step verifies that the device is the corporate device enrolled in Intune. If the serial number on the device does not match, the wrong device was selected. The user should go back to the previous screen and select a different device.

7. After the serial number is verified, the Company Portal app redirects to the Company Portal website to finalize enrollment. Then the website prompts the user to return to the app.

8. Enrollment is now complete. The user can now use this device with the full set of capabilities.

### About corporate-owned managed devices with no user affinity

Devices that are configured with no user affinity do not support the Company Portal and should not have the app installed. The Company Portal is designed for users who have corporate credentials and require access to personalized corporate resources (e.g. email). Devices that are enrolled with no user affinity are not intended to have a dedicated user sign in. Kiosk, point of sale (POS), or shared-utility devices are typical use cases for devices that are enrolled with no user affinity.

If user affinity is required, be sure that the device’s enrollment profile has **User Affinity** selected before enrolling the device. To change the affinity status on a device, you must retire the device and reenroll it.

