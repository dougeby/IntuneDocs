---
# required metadata

title: Enroll corporate-owned iOS devices | Microsoft Intune
description: Enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or Apple Configurator
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll corporate-owned iOS devices in Microsoft Intune
Microsoft Intune supports the enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.

**Prerequisite:**  [Apple Push Notification service  certificate](set-up-ios-and-mac-management-with-microsoft-intune.md)

You can enroll corporate-enrolled iOS devices in three ways:

-   **Apple Configurator** - iOS devices can be enrolled by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac running Apple Configurator. Apple Configurator supports two forms of enrollment:

    - **Setup Assistant Enrollment** – Factory resets the device and prepares it for setup by the device’s new user. This method requires the administrator to USB connect the iOS device to a Mac computer running [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) to preconfigure the enrollment. Devices are then delivered to their users who run the Setup Assistant process, configuring the device with their work or school credentials and completing the enrollment process. [Enroll iOS devices using Apple Configurator and Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Direct Enrollment** – Creates an Apple Configurator-compliant file for use during device preparation. The enrolled device isn’t factory reset but has no user affiliation. This method requires the administrator to USB connect the iOS device to a Mac computer running [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) to enroll the device. [Enroll iOS devices using Apple Configurator Direct Enrollment](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** – Deploys an enrollment profile “over the air” to devices purchased through Apple's Device Enrollment Program. When the user runs Setup Assistant on the device, the device is enrolled in Intune.  Devices enrolled through DEP cannot be un-enrolled by users. [Enroll Device Enrollment Program iOS devices](ios-device-enrollment-program-in-microsoft-intune.md)

## Using Company Portal on DEP or Apple Configurator-enrolled devices

Devices configured with user affinity can install and run the Company Portal app to download apps and manage devices. Once users receive their devices they must complete a number of additional steps to complete the Setup Assistant and install the Company Portal app.

How to enroll corporate-owned iOS devices with user affinity
1. When users power on their device, they are prompted to complete the Setup Assistant. During setup, users are prompted for their credentials. They must use the credentials (i.e. the unique personal name or UPN) associated with their subscription in Intune.

2. During setup, users are prompted for an Apple ID. An Apple ID must be provided to allow the device to install the Company Portal. An Apple ID can also be provided after setup is complete from the iOS settings menu.

3. After completing setup, the iOS device must install the Company Portal app from the App Store, for example Company Portal app.

4. The user can now login to the Company Portal using the UPN used when setting up the device.

5. After logging in, the user is prompted to enroll their device. The first step is to Identify their device. The app presents a list of iOS devices that have already been corporate-enrolled and assigned to the end-user’s Intune account. Choose the matching device.

  If this device is not already corporate-enrolled, select “new device” to continue with the standard enrolment flow.

6. On the next screen, the user must confirm the serial of the new device. The user can tap on the link “confirm the Serial Number” to launch the Settings app to verify the serial number. The user must then enter the last 4 characters of the serial number into the Company Portal app.

  This step verifies that the device is the corporate device enrolled in Intune. If the serial number on the device does not match, the wrong device was selected. Go back to the previous screen and select a different device.

7. After the serial number is verified, the Company Portal app redirects to the Company Portal website to finalize enrolment, and then prompts the user to return to the app.

8. Enrollment is now complete. You can now use this device with the full set of capabilities.

### About corporate-owned managed devices with no user affinity

Devices configured with no user affinity do not support the Company Portal and should not install the app. The Company Portal is designed for users who have corporate credentials and require access to personalized corporate resources (e.g. email). Device enrolled with no user affinity are not intended to have a dedicated user sign in. Kiosk, point of sale (POS), or shared utility devices are typical use-cases for devices enrolled with no user affinity. If user affinity is required, be sure the device’s enrollment profile has User Affinity selected prior to enrolling the device. To change the affinity status on a device you must retirement and re-enroll the device.



### See also
[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
