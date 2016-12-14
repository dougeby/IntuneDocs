---
# required metadata

title: Enroll iOS devices with Apple Configurator and direct enrollment | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to use the Apple Configurator to enroll corporate-owned iOS devices with direct enrollment."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll iOS devices with Apple Configurator and direct enrollment

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) running on a Mac computer. This process does not factory-reset the device and enrolls the device with a predefined policy. This method is for devices with **no user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment..  

When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number. You can also name the device for identification purposes before Intune captures the device name during enrollment. The Company Portal app is not supported for directly enrolled devices. This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.

## Prerequisites

Complete the following prerequisites before setting up iOS device enrollment:

- Enable connections (more information coming soon)
- [Set the MDM Authority](set-mdm-authority.md)
- Create groups (more information coming soon)
- [Configure the Company Portal](company-portal-app.md)
- Assign user licenses (more information coming soon)
- [Get an Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)
- Physical access to iOS devices
- Device serial numbers—see [How to get an iOS serial number](https://support.apple.com/en-us/HT204308)
- USB connection cables
- A Mac computer with Apple Configurator 2.0

## Create an Apple Configurator profile for devices

A device enrollment profile defines the settings applied to a group of devices. The following steps show how to create a device enrollment profile for iOS devices enrolled by using Apple Configurator.

1. In the **Enrollment** blade, choose **Apple Enrollment**.

2. Under **Manage Apple Configurator Enrollment Settings**, select **AC Profiles**.

3. On the **Apple Configurator Enrollment Profiles** blade, select **Create**.

4. On the **Create Enrollment Profile** blade, enter a name and description for the profile.

5. For **User Affinity** choose **Enroll without user affinity** to ensure that the device is not affiliated with a user. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.

6. Select **Create** to save the profile.

## Export the profile as .mobileconfig to iOS devices

1. On the **Export Profile** blade, download the enrollment profile to [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to push directly as a management profile to a connected iOS device. This method does not do a factory reset of the device.

2. Prepare the device with Apple Configurator by using the following steps. 

   a. On a Mac computer, open Apple Configurator 2.0.

   b. Connect the iOS device to the Mac computer with a USB cord. Close Photos, iTunes, and other apps that open for the device when the device is detected.

   c. In Apple Configurator, choose the connected iOS device, and then choose the **Add** button. Options that can be added to the device appear in the drop-down list. Choose **Profiles**.

   d. Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**. The profile is added to the device. If the device is Unsupervised, the installation will require acceptance on the device.

3. Use the following steps to install the profile on the iOS device. The device must have already completed the Setup Assistant and be ready to use. If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.

   a. Unlock the iOS device.

   b. In the **Install profile** dialog box for **Management profile**, choose **Install**.

   c. Provide the Device Passcode or Apple ID, if required.

   d. Accept the **Warning**, and choose **Install**.

   e. Accept the **Remote Warning**, and choose **Trust**.

   f. When the **Profile Installed** box confirms the profile as Installed, choose **Done**.

4. On the iOS device, open **Settings** and go to **General** > **Device Management** > **Management Profil**e. Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps. Policy restrictions and apps might take up to 10 minutes to appear on the device.

5. Distribute devices. The iOS device is now enrolled with Intune and managed.
