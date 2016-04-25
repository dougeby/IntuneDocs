---
# required metadata

title: Set up iOS and Mac management with Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Set up iOS and Mac device management
With Microsoft Intune, you can enable BYOD ("bring your own device") for iOS and Mac OS X device enrollment to give access to company email and apps to iPhone, iPad and Mac users. Once enrolled, users can install the Intune Company Portal app and their devices can be targeted with policy using the Intune administration console.

Before you can manage iOS devices with Intune, the devices must be able to communicate with Intune. Apple requires a trust relationship with Intune established by importing an Apple Push Notification service (APNs) certificate.

1.  **Set up Intune**<br>
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) as **Microsoft Intune** and setting up MDM.

2.  **Get a certificate signing request**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and click **Download the APNs certificate request**. Save the certificate signing request (.csr) file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.

    ![](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Get an Apple Push Notification service certificate**<br>
    Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) and sign in with your company Apple ID to create the APNs certificate using the .csr file. After clicking **Upload** on Apple's Push Certificate Porta, you will receive a .json file which cannot be used for APNs. Complete the download and return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers** and click **Download**.

    Download the APNs (.pem) certificate and save the file locally. This Apple ID must be used in future to renew your APNs certificate.

4.  **Add the APNs certificate to Intune**<br>
    In the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and click **Upload the APNs certificate**. **Browse** to the certificate (.pem) file and click **Open** and then enter your **Apple ID**. With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.

5.  **Tell users how to get access to company resources with the company portal**<br>
    Your users will need to know how to enroll their devices and what to expect once they're brought into management. [What to tell your end users about using Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

If your company or organization purchases iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### See Also
[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
