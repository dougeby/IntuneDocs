---
# required metadata

title: Set up Android management 
description: Enable mobile device management (MDM) for Android and KNOX Standard devices with Microsoft Intune.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: lacranda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Set up Android device management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As an Intune administrator, you can enable management of Android devices, including Samsung Knox Standard devices, from the Company Portal. Users can then enroll their devices using the Company Portal app that is available from Google Play.

By default, Android devices are allowed to enroll in Intune. To block Android devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials. Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the **Allow Android devices** check box.

1.  **Set up Intune**<br>
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.

2.  **Android enrollment enabled**<br>
    No additional configurations in the Intune console are needed to enable Android mobile device enrollment.

3.  **Tell your users how to enroll their devices to get access to company resources.**

	For end-user enrollment instructions, see [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.

	For information about other end-user tasks, see these articles:
  - [Resources about the end-user experience with Microsoft Intune](/intune/end-user-educate)
  - [End user guidance for Android devices](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Due to the absence of Google Play Store in China, Android devices must obtain the Company Portal from Chinese app marketplaces. The Company Portal app for Android will be available for download on the following stores:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service. Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete. 

|Intune Admin Console| Intune Company Portal app for Android |Intune Company Portal Website|   
|---|---|---|
|Full wipe| Remove a remote device| Remove device (local and remote)|
|Selective wipe| Reset device| Reset device|
|New or updated app deployments| Install available line-of-business apps| Device passcode reset|
|Remote lock|||
|Passcode reset|||

### See also
[Prerequisites to enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md)
