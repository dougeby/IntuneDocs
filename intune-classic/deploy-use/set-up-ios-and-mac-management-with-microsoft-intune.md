---
# required metadata

title: Set up iOS and Mac management 
description: Enable mobile device management (MDM) for iOS devices including iPads and iPhones as well as Mac OS X devices with Microsoft Intune.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
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
ms.custom: intune-classic

---

# Set up iOS and Mac device management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune enables mobile device management (MDM) of iPads, iPhones, and macOS devices and gives users access to company email and apps. An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices. After the certificate is added to Intune, users can install the Company Portal app to enroll their devices, or the admin can set up [corporate-owned iOS device management](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Set up Intune**<br>
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.

2.  **Get a certificate signing request**<br>
    As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**. Save the certificate signing request (.csr) file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.

    ![Upload APNs certificate dialog box](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Get an Apple Push Notification service certificate**<br>
    Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign in with your company Apple ID to create the APNs certificate by using the .csr file. After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file that cannot be used for APNs. Complete the download, return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers**, and then choose **Download**.

    Download the APNs (.pem) certificate, and save the file locally.

	> [!NOTE]
	> Every year, you need to renew (not replace) this APNs certificate. Use this same Apple ID to sign in to Apple's Push Certificate Portal to renew the certificate, and then use the same instructions in this topic to download the certificate, and then upload it to Intune.

4.  **Add the APNs certificate to Intune**<br>
    In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**. Go to the certificate (.pem) file, choose **Open**, and then enter your **Apple ID**. With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.

5.  **Tell your users how to enroll their devices to get access to company resources.**

    For end-user enrollment instructions, see [Enroll your iOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) and [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos). The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.

	For information about other end-user tasks, see these articles:
    - [Resources about the end-user experience with Microsoft Intune](/intune/end-user-educate)
    - [End user guidance for iOS and Mac devices](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

If your company or organization buys iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### See Also
[Prerequisites for enrollment with Microsoft Intune](prerequisites-for-enrollment.md)
