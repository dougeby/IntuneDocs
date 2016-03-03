---
title: Enroll mobile devices and install an app
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---
# 9. Enroll mobile devices and install an app
To set up mobile device management with Intune, you must first set the mobile device management authority, enable management for device platforms, and enroll your devices with the company portal app. You can then deploy the Microsoft Skype application that you published in step 6.

## Enable device management and enroll devices

1.  **Make Intune your mobile device management authority**
    In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.  Choose **Yes** in the MDM Authority dialog box.

2.  **Enable MDM for your device platform**
    Enable mobile device management for the device platform you want to manage. Depending on your platform, different requirements are needed:

    -   **iOS and Mac OS X**: see [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).

    -   **Windows Phone**: see [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

    -   **Android**: Android mobile devices allow users to enroll using the company portal app available from Google Play. No additional configuration in Intune is required.

3.  **Enroll devices**:

    -   **Android** - Install the **Intune Company Portal** app from Microsoft Corporation available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) and sign in with the Intune user credentials added above.

    -   **iOS and Mac OS X** - Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with the Intune user credentials added above. View **Enrolled devices** to add your device.

    -   **Windows Phone 8.1**- Users install the **Company Portal** app from Microsoft Corporation available in the Windows Phone store and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

    -   **Windows Phone 8.0**  - Users choose **system settings** &gt; **company apps**, and sign in with Intune user credentials added above. The company portal app is deployed to your phone.

    If prompted for a **Server address**, type “manage.microsoft.com”.

4.  Open the company portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.

To learn more about mobile device management using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], see [Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md).


## Next steps
Congratulations! You have just completed the last step of the *Get started with a paid subscription to Microsoft Intune* guide. Now that your initial configuration is complete, you can consider enabling additional MDM functionality.

>[!div class="step-by-step"]
>[Next](.\post-configuration-tasks.md)  **Post-configuration tasks**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-8.md)  **Enroll computers in Intune**
