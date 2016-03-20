---
title: Company Portal Frequently Asked Questions
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
author: Staciebarker
---
# Company Portal Frequently Asked Questions

## Company Portal FAQ

-   [What is the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_WhatIs)

-   [What can I do with the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_WhatCanIDo)

-   [What happens when I add a computer or device to the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_AddDevice)

-   [What kind of computers or devices can I add to the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_WhatCanIAdd)

-   [Can I remove a computer or device from the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_RemoveDevice)

-   [Why don’t I see all of my devices in the company portal?](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_CantSeeDevices)

-   [I need to install a new version of the company portal](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_InstallNewVersion)

-   [I receive an error that my computer is already enrolled](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_NotEnrolled)

-   [Troubleshooting iPhone error messages during enrollment](../Topic/Company-Portal-Frequently-Asked-Questions.md#BKMK_TroubleshootingiOS)

### <a name="BKMK_WhatIs"></a>What is the company portal?
The company portal is your company’s interface that lets you manage your work computers and devices, or manage your personal computers or devices that you choose to use at work.  The company portal can be a website that you go to, or can be an app that you install to your device.

### <a name="BKMK_WhatCanIDo"></a>What can I do with the company portal?
Once you add your computer or device to the company portal, you can browse for company apps to install, manage other devices that you have added, and find contact information for your IT administrator.

### <a name="BKMK_AddDevice"></a>What happens when I add a computer or device to the company portal?
When you add a computer or device to the company portal, some software may be installed or an app may be downloaded (depending on the device).  You are also giving your IT administrator permission to manage your device to help protect the company information on the device.  For more information, see [What Happens if You Add a Device to the Company Portal](http://go.microsoft.com/fwlink/?LinkID=265350).

### <a name="BKMK_WhatCanIAdd"></a>What kind of computers or devices can I add to the company portal?

-   Windows 8.1 devices

-   Windows RT devices

-   Windows Phone 8

-   Windows Phone 8.1

-   iPhones and iPads

-   Android devices

### <a name="BKMK_RemoveDevice"></a>Can I remove a computer or device from the company portal?
Yes, you can either remove or reset a computer or device from the company portal.  There is a difference between **remove** and **reset**:

-   When you remove a computer or device, you won’t be able to access the company portal from that device anymore, and some company data may be removed from your device.

-   When you reset a computer or device, the company portal attempts to reset your computer or device back the manufacturer’s default settings.  This may result in all data, both company data and personal data, being removed.

For more information, see [What Happens if You Remove or Reset a Device Using the Company Portal](http://go.microsoft.com/fwlink/?LinkID=260958).

### <a name="BKMK_CantSeeDevices"></a>Why don’t I see all of my devices in the company portal?
In order to see a device, it must be added to the company portal. Browse to the company portal as directed by your administrator and follow the steps for your device. You also won’t see devices that are owned and managed by your company.

### <a name="BKMK_InstallNewVersion"></a>I need to install a new version of the company portal
If your version of the company portal is no longer supported, or there is a newer version of the company portal available, use the following procedures to update your device.

##### To update your Windows device

1.  Navigate to the Windows Store and search for **company portal**.

2.  Follow the installation directions.

    > [!NOTE]
    > If you are unable to access the Windows Store, contact your administrator.

##### To update your iOS device

1.  The Apple AppStore will alert you when a new version of the company portal is available. Follow the directions in the alert to update your device.

### <a name="BKMK_NotEnrolled"></a>I receive an error that my computer is already enrolled
This means that your computer is already added to the company portal, but is not linked to your user account yet. Follow this procedure to link your computer to your user account and complete the process.

##### To link your computer

1.  On the computer that you wish to link to your account, click **Start** then click **Microsoft Intune Center**.

2.  Open the company portal.

3.  Follow the prompts to link the computer to your user account.

### <a name="BKMK_TroubleshootingiOS"></a>Troubleshooting iPhone error messages during enrollment
If you encounter errors while enrolling your iPhone, follow the instructions below.

#### DeviceCapReached
**Issue:** This message indicates that you have too many mobile devices enrolled already.

**Workaround:** Before you enroll another mobile device, you must remove one of your currently enrolled mobile devices from the company portal.

#### APNSCertificateNotValid
**Issue:** This message indicates that there is a problem with the certificate that allows your mobile device to communicate with your company’s network.

**Workaround:** Contact your IT administrator and tell them that you received the message **APNSCertificateNotValid** while trying to enroll your mobile device, and to see the solution at [Troubleshooting iOS Enrollment Errors with Microsoft Intune or System Center 2012 R2 Configuration Manager](http://go.microsoft.com/fwlink/?LinkID=327928).

#### AccountNotOnboarded
**Issue:** This message indicates that there is a problem with the certificate that allows your mobile device to communicate with your company’s network.

**Workaround:** Contact your IT administrator and tell them that you received the message **AccountNotOnboarded** while trying to enroll your mobile device, and to see the solution at [Troubleshooting iOS Enrollment Errors with Microsoft Intune or System Center 2012 R2 Configuration Manager](http://go.microsoft.com/fwlink/?LinkID=327928).

#### DeviceTypeNotSupported
**Issue:** This message indicates that the mobile device type that you are trying to enroll is not supported.

**Workaround:** Contact your IT administrator and tell them that you received the message **DeviceTypeNotSupported** while trying to enroll your mobile device, and to see the solution at [Troubleshooting iOS Enrollment Errors with Microsoft Intune or System Center 2012 R2 Configuration Manager](http://go.microsoft.com/fwlink/?LinkID=327928).

#### UserLicenseTypeInvalid
**Issue:** This message indicates that you cannot enroll your mobile device because your user account is not yet a member of a required user group.

**Workaround:** Contact your IT administrator and tell them that you received the message **UserLicenseTypeInvalid** while trying to enroll your mobile device, and to see the solution at [Troubleshooting iOS Enrollment Errors with Microsoft Intune or System Center 2012 R2 Configuration Manager](http://go.microsoft.com/fwlink/?LinkID=327928).

#### MdmAuthorityNotDefined
**Issue:** This message indicates that your IT administrator needs to configure the way the mobile devices in your company are managed.

**Workaround:** Contact your IT administrator and tell them that you received the message **MdmAuthorityNotDefined** while trying to enroll your mobile device, and to see the solution at [Troubleshooting iOS Enrollment Errors with Microsoft Intune or System Center 2012 R2 Configuration Manager](http://go.microsoft.com/fwlink/?LinkID=327928).

