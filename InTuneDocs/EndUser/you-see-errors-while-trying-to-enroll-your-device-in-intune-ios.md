---
# required metadata

title: You see errors while trying to enroll your iOS device in Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# You see errors while trying to enroll your iOS device in Intune

The following table lists errors that you might see while enrolling your iOS device in Intune. Share this link with your It administrator. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

|Error message|Issue|What to tell your IT administrator|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|No enrollment policy|Check that all enrollment prerequisites have been configured, such as the APNs certificate, and that "iOS as a platform" is enabled. For instructions, see [Set up iOS and Mac device management](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|You have too many mobile devices enrolled already.|The user must remove one of his or her currently enrolled mobile devices from the Company Portal before enrolling another. See the instructions for the type of device you're using: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios), [Windows](unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|There is a problem with the certificate that allows your mobile device to communicate with your company’s network.<br /><br />Contact your IT administrators and tell them that you received the message **APNSCertificateNotValid** while trying to enroll your mobile device, and tell them to see the resolution in this table.|The Apple Push Notification Service (APNS) provides a channel to reach out to enrolled iOS devices. If the steps to obtain an APNS certificate were not performed, or the APNS certificate has expired, then enrollment attempts will fail, and this message will appear.<br /><br />Review the information on setting up users in [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and [organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|There is a problem with the certificate that allows your mobile device to communicate with your company’s network.<br /><br />Contact your IT administrators and tell them that you received the message **APNSNotOnboarded** while trying to enroll your mobile device, and tell them to see the resolution in this table.|The Apple Push Notification Service (APNS) provides a channel to reach out to enrolled iOS devices. If the steps to obtain an APNS certificate were not performed, or the APNS certificate has expired, then enrollment attempts will fail, and this message will appear.<br /><br />For more information, review [Set up iOS and Mac management with Microsoft Intune](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|You may have tried to enroll using a non-iOS device. The mobile device type that you are trying to enroll is not supported.<br /><br />Ensure that your device is running iOS version 7.1 or later.<br /><br />Contact your IT administrators and tell them that you received the message **DeviceTypeNotSupported** while trying to enroll your mobile device, and tell them to see the resolution in this table.|Ensure that your user's device is running iOS version 7.1 or later.|
|UserLicenseTypeInvalid|You cannot enroll your mobile device because your user account is not yet a member of a required user group.<br /><br />Contact your IT administrators and tell them that you received the message **UserLicenseTypeInvalid** while trying to enroll your mobile device, and tell them to see the resolution in this table.|Before users can enroll their devices, they  must be a member of the right user group. This message means that they have the wrong license type for the designated mobile device management authority. For example, if Intune has been designated as the mobile device management authority, and they are using a System Center 2012 R2 Configuration Manager license, they will see this error.<br /><br />Review the following for more information:<br /><br />Review [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) and information about setting up users in [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3 and [organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Your IT administrator needs to configure the way that mobile devices in your company are managed.<br /><br />Contact your IT administrators and tell them that you received the message **MdmAuthorityNotDefined** while trying to enroll your mobile device, and tell them to see the resolution in this table.|The mobile device management authority has not been designated in Intune.<br /><br />Review item #1 in the section "Step 6: Enroll mobile devices and install an app" in [Get started with a 30-day trial of Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### See also
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)