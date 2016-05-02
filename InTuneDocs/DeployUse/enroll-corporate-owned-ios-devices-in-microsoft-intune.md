---
# required metadata

title: Enroll corporate-owned iOS devices in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll corporate-owned iOS devices in Microsoft Intune
Microsoft Intune supports the enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.

You can enroll corporate-enrolled iOS devices in three ways:

-   **Setup Assistant Enrollment** – Factory resets the device and prepares it for setup by the device’s new user. This method requires the administrator to USB connect the iOS device to a Mac computer running Apple Configurator to preconfigure the enrollment. Devices are then delivered to their users who run the Setup Assistant process, configuring the device with their work or school credentials and completing the enrollment process. [Enroll iOS devices using Apple Configurator and Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Direct Enrollment** – Creates an Apple Configurator-compliant file for use during device preparation. The enrolled device isn’t factory reset but has no user affiliation. This method requires the administrator to USB connect the iOS device to a Mac computer running Apple Configurator to enroll the device. [Enroll iOS devices using Apple Configurator Direct Enrollment](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** – Deploys an enrollment profile “over the air” to devices purchased through Apple's Device Enrollment Program. When the user runs Setup Assistant on the device, the device is enrolled in Intune.  Devices enrolled through DEP cannot be un-enrolled by users. [Enroll Device Enrollment Program iOS devices](ios-device-enrollment-program-in-microsoft-intune.md)




### See also
[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
