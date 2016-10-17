---
# required metadata

title: Set up iOS and Mac management | Microsoft Intune
description: Enable mobile device management (MDM) for iOS devices including iPads and iPhones as well as Mac OS X devices with Microsoft Intune.
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Set up iOS and Mac device management
For help to set up your iOS or Mac device, see [Using your iOS or Mac OS X device with Intune](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md).

Intune enables mobile device management (MDM) of iPads, iPhones, and Mac OS X devices and gives users access to company email and apps. An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices. After the certificate is added to Intune, users can install the Company Portal app to enroll their devices, or the admin can set up [corporate-owned iOS device management](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Set up Intune**<br>
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#set-mobile-device-management-authority) as **Microsoft Intune** and setting up MDM.

2.  **Get a certificate signing request**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**. Save the certificate signing request (.csr) file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.

    ![Upload APNs certificate dialog box](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Get an Apple Push Notification service certificate**<br>
    Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign in with your company Apple ID to create the APNs certificate by using the .csr file. After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file that cannot be used for APNs. Complete the download, return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers**, and then choose **Download**.

    Download the APNs (.pem) certificate, and save the file locally. This Apple ID must be used later to renew your APNs certificate.

4.  **Add the APNs certificate to Intune**<br>
    In the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**. Go to the certificate (.pem) file, choose **Open**, and then enter your **Apple ID**. With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.

5.  **Tell users how to get access to company resources with the company portal**<br>
    Your users will need to know how to enroll their devices and what to expect after they're brought into management.
    - [What to tell your end users about using Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [End user guidance for iOS and Mac devices](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

If your company or organization buys iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### See Also
[Prerequisites for enrollment with Microsoft Intune](prerequisites-for-enrollment.md)
