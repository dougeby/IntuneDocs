---
# required metadata

title: You see errors while trying to enroll your iOS device in Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: angrobe
ms.date: 08/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# You see errors while trying to enroll your iOS device in Intune

The following table lists errors that you might see while enrolling your iOS device in Intune. Share this link with your It admin. For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

|Error message|Issue|What to tell your IT admin|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|No enrollment policy|Check that all enrollment prerequisites, like the Apple Push Notification Service (APNs) certificate, have been set up and that "iOS as a platform" is enabled. For instructions, see [Set up iOS and Mac device management](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|You have too many mobile devices enrolled already.|The user must remove one of his or her currently enrolled mobile devices from the Company Portal before enrolling another. See the instructions for the type of device you're using: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|There is a problem with the certificate that lets your mobile device communicate with your company’s network.<br /><br />Contact your IT admins, tell them that you received the **APNSCertificateNotValid** message when you tried to enroll your mobile device, and tell them to see the resolution in this table.|The Apple Push Notification Service (APNs) provides a channel to reach out to enrolled iOS devices. If the steps to get an APNs certificate were not performed, or if the APNs certificate has expired, then enrollment attempts will fail, and this message will appear.<br /><br />Review the information about how to set up users in [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and [organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|There is a problem with the certificate that lets your mobile device communicate with your company’s network.<br /><br />Contact your IT admins, tell them that you received the **APNSNotOnboarded** message when you tried to enroll your mobile device, and tell them to see the resolution in this table.|The Apple Push Notification Service (APNs) provides a channel to reach out to enrolled iOS devices. If the steps to get an APNs certificate were not performed, or if the APNs certificate has expired, then enrollment attempts will fail, and this message will appear.<br /><br />For more information, review [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|You might have tried to enroll using a non-iOS. The mobile device type that you are trying to enroll is not supported.<br /><br />Ensure that your device is running iOS version 8.0 or later.<br /><br />Contact your IT admins, tell them that you received the **DeviceTypeNotSupported** message when you tried to enroll your mobile device, and tell them to see the resolution in this table.|Ensure that your user's device is running iOS version 8.0 or later.|
|UserLicenseTypeInvalid|You cannot enroll your mobile device because your user account is not yet a member of a required user group.<br /><br />Contact your IT admins, tell them that you received the **UserLicenseTypeInvalid** message when you tried to enroll your mobile device, and tell them to see the resolution in this table.|Before users can enroll their devices, they  must be members of the right user group. This message means that they have the wrong license type for the designated mobile device management authority. For example, if Intune has been designated as the mobile device management authority, and they are using a System Center 2012 R2 Configuration Manager license, they will see this error.<br /><br />Review the following for more information:<br /><br />Review [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) and information about how to set up users in [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and [organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Your IT admin needs to set up the way that mobile devices in your company are managed.<br /><br />Contact your IT admins, tell them that you received the **MdmAuthorityNotDefined** message when you tried to enroll your mobile device, and tell them to see the resolution in this table.|The mobile device management authority has not been designated in Intune.<br /><br />Review item #1 in the "Step 6: Enroll mobile devices and install an app" section in [Get started with a 30-day trial of Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|
