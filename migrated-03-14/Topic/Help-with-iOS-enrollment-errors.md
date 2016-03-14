---
title: Help with iOS enrollment errors
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c91075e8-e184-49a9-bedf-4a213872613f
robots: noindex,nofollow
---
# Help with iOS enrollment errors
This topic helps you to work around iOS enrollment errors.

## iOS enrollment errors
The following table lists errors that users might encounter while enrolling iOS devices. Possible cause and solution details are provided for each error.

|Error message|Possible cause|Resolution using [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]|Resolution using System Center 2012 R2 Configuration Manager|
|-----------------|------------------|--------------------------------------------------------------------------|----------------------------------------------------------------|
|DeviceCapReached|This message indicates that the user has too many mobile devices enrolled already.|Before the user enrolls another mobile device, they must remove one of their currently enrolled mobile devices from the company portal.|Before the user enrolls another mobile device, they must remove one of their currently enrolled mobile devices from the company portal.|
|APNSCertificateNotValid|The Apple Push Notification Service (APNS) provides a channel to reach out to enrolled iOS devices. If the steps to obtain an APNS certificate were not performed, or the APNS certificate has expired, then enrollment attempts will fail with this message.|Review the “External dependencies for enrolling iOS devices” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|Review the “External dependencies for enrolling iOS devices” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|
|AccountNotOnboarded|The Apple Push Notification Service (APNS) provides a channel to reach out to enrolled iOS devices. If the steps to obtain an APNS certificate were not performed then enrollment attempts will fail with this message.|Review the “External dependencies for enrolling iOS devices” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|Review the “External dependencies for enrolling iOS devices” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|
|DeviceTypeNotSupported|You may get this message if you attempt to enroll using a non-iOS device.|Ensure that the device is running iOS version 5.0 or later.|Ensure that the device is running iOS version 5.0 or later.|
|UserLicenseTypeInvalid|Before users are able to enroll their devices, they must be members of the appropriate user group. This message indicates that the user has the wrong license type for the designated mobile device management authority. For example, if [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] has been designated as your mobile device management authority, and the user is using a System Center 2012 R2 Configuration Manager license, you will receive this error.|Review the “Provision users for device enrollment” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|Review the “Provision users for device enrollment” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|
|MdmAuthorityNotDefined|This message indicates that the mobile device management authority has not been designated in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].|Review the “Set the Mobile Device Management Authority for Microsoft Intune” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|Review the “Set the Mobile Device Management Authority for Microsoft Intune” section in the document [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md)|
