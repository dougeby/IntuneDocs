---
# required metadata

title: Enroll mobile devices and install an app | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll mobile devices and install an app
To set up mobile device management with Intune, you must first set the mobile device management authority, enable management for device platforms, and enroll your devices with the Company Portal app. You can then deploy the Microsoft Skype application that you published in step 6.

## Enable device management and enroll devices

1.  **Make Intune your mobile device management authority**
    In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.  Choose **Yes** in the MDM Authority dialog box.
	![Admin console. Set mdm to Intune](./media/mdmAuthority.png)

2.  **Enable MDM for your device platform**
    Enable mobile device management for the device platform you want to manage. Depending on your platform, different requirements are needed:

    -   **iOS and Mac OS X**: see [Set up iOS and Mac management with Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: see [Set up Windows Phone management with Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: Android mobile devices allow users to enroll using the Company Portal app available from [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). No additional configuration in Intune is required.

3.  **Enroll devices**:

    -   **Android** - Install the **Intune Company Portal** app from Microsoft Corporation available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), and sign in with the Intune user credentials added above.

    -   **iOS and Mac OS X** - Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with the Intune user credentials added above. View **Enrolled devices** to add your device.

    -   **Windows Phone 8.1**- Users install the **Company Portal** app from Microsoft Corporation available in the Windows Phone store and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

    -   **Windows Phone 8.0**  - Users choose **system settings** &gt; **company apps**, and sign in with Intune user credentials added above. The Company Portal app is deployed to your phone.

    If prompted for a **Server address**, type “manage.microsoft.com”.

## Install an app on an enrolled device
In [step 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) of this quick start guide, you published the Skype app to your custom Intune Users group. Now you'll install that app on a newly enrolled device.

Open the Company Portal on the enrolled mobile device, choose **Apps**, and then install **Microsoft Skype**.

To learn more about mobile device management using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], see [Get ready to enroll devices in Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).


### Next steps
Congratulations! You have just completed the last step of the *Intune quick start guide*. Now that your initial configuration is complete, you can consider enabling additional MDM functionality.

>[!div class="step-by-step"]

>[&larr; **Enroll devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Post-configuration tasks** &rarr;](.\post-configuration-tasks.md)  
