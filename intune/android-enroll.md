---
# required metadata

title: Enroll Android devices in Intune
titlesuffix: "Microsoft Intune"
description: Learn how to enroll Android devices in Intune.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll Android devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As an Intune administrator, you can manage the following Android devices:
- Android devices, including Samsung Knox Standard devices.
- Android enterprise devices, including [Android work profile devices](#enable-enrollment-of-android-for-work-devices) and Android kiosk devices.

Devices that run Samsung Knox Standard are supported for multi-user management by Intune. This means that users can sign in and out of a device with their Azure AD credentials. The device is centrally managed whether it’s in use or not. When users sign in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.

## Prerequisite

To prepare to manage mobile devices, you must set the mobile device management (MDM) authority to **Microsoft Intune**. See [Set the MDM authority](mdm-authority-set.md) for instructions. You set this item only once, when you are first setting up Intune for mobile device management.

## Set up Android enrollment

By default, Intune allows enrollment of Android and Samsung Knox Standard devices. After fulfilling the prerequisite, admins merely need to [tell their users how to enroll their devices](/intune-user-help/enroll-your-device-in-intune-android).

After a user has enrolled, you can begin managing their devices in Intune, including [assigning compliance policies](compliance-policy-create-android.md), [managing apps](app-management.md), and more.

For information about other user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](end-user-educate.md)
- [Using your Android device with Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

To block Android devices, or to block only personally owned Android devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).

## Set up Android enterprise enrollment

Android enterprise is a set of Android device features and services that separate personal apps and data from a work profile containing work apps and data. Android enterprise devices include work profile devices and kiosk devices. 

To set up enrollment for Android enterprise devices, you must first [connect Android enterprise to Intune](connect-intune-android-enterprise.md). After completing this step, you can:

[Set up Android work profile enrollments](android-work-profile-enroll.md)
[Set up Android kiosk enrollments](android-kiosk-enroll.md)

## End user experience when enrolling a Samsung Knox device
There are several considerations when enrolling Samsung Knox devices:
-	Even if no policies require a PIN, the device must have at least a four-digit PIN to enroll. If the device does not have a PIN, the user will be prompted to create one.
-	There is no user interaction for Workplace Join Certificates (WPJ).
-	The user is prompted with Service Enrollment info and what the app can do.
-	The user is prompted with Knox Enrollment info and what Knox can do.
-	If an Encryption Policy is enforced, users are required to set a six Character Complex password for the device passcode.
-	There are no additional user prompts to install certificates pushed by a service for Company Resource Access.
- Some older Knox devices will prompt the user for additional certificates used for Company Resource Access.
- If a Samsung Mini device fails to install the WPJ with either the **Certificate Not Found** or **Unable to Register Device** errors, install the latest Samsung Firmware Updates.
