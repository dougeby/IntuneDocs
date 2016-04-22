---
# required metadata

title: Enroll trial mobile devices | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Step 5: Enroll trial mobile devices and install an app
To set up mobile device management with Intune, you must  first set the mobile device management authority,  enable management for device platforms, and enroll your devices with the Company Portal app. You can then deploy the Microsoft Skype application that you published.

## Prepare the service for device management

1.  **Make Intune your mobile device management authority**

    In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** &gt; **Mobile Device Management**. Choose **Tasks** > **Set MDM Authority**, and then choose **Yes** in the **MDM Authority** dialog box.

2.  **Enable MDM for your device platform**

    Enable mobile device management for the device platform you want to manage. Depending on your platform, different requirements are needed:

    -   **iOS and Mac OS X**: see [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: Android mobile devices allow users to enroll using the Company Portal app available from Google Play. No additional configuration in Intune is required.

    -   **Windows Phone**: see [Set up Windows Phone management with Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Enroll test devices

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.

### Android
Install the **Intune Company Portal** app from Microsoft Corporation, available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), and sign in with the Intune user credentials added above.

### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

 ### Windows Phone 8.0
 Users click **system settings** &gt; **company apps**, and sign in with Intune user credentials added above. The Company Portal app is deployed to your phone.

If prompted for a **Server address**, type “manage.microsoft.com”.


## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.

To learn more about mobile device management using Intune, see [Get ready to enroll devices in Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).

### Next steps
Congratulations! You have just completed step 5 of the *Get started with a 30-day trial of Microsoft Intune* walkthrough.

>[!div class="step-by-step"]

>[&larr; **Create Policies**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Options and extras** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  
