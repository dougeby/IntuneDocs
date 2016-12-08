---
# required metadata

title: Enable device enrollment | Microsoft Intune
description: Set MDM authority and enable enrollment for iOS, Windows, Android, and Mac devices.
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
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
To set up mobile device management with Intune, you must first set the *mobile device management authority*, which identifies the service that can manage devices associated with your account. This guidance assumes you will use the Intune service instead of System Center Configuration Manager. Once the MDM authority is set, you can enable management for device platforms, and enroll your devices with the Company Portal app.

## Enable device enrollment

1. **Make Intune your mobile device management authority**
    In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.  

2. Choose **Yes** in the MDM Authority dialog box.

	![Admin console. Set mdm to Intune](./media/mdmAuthority.png)

## Choose how to enroll devices

Intune can manage devices in a variety of ways depending upon your company's requirements. "Bring your own device" (BYOD), corpoarte-owned devices, "choose your own device" (CYOD), and kiosk-mode devices are just a few available enrollment scenarios.

Follow these steps to [Choose how to enroll devices](choose-how-to-enroll-devices1.md).

## Enable MDM for your device platform
Enrollment must be enabled for iOS, Mac, and Android for Work devices establishing a relationship between the platform provider and your Intune tenant. Windows and Android devices do not require additional steps, but for Windows devices you can simplify device enrollment for your users by creating a special DNS registry entry.

Enable device enrollment for the device platform you want to manage. Depending on your platform, different requirements are needed:

-  [iOS and macOS](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Window PC](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Window 10 Mobile and Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Once enrollment is enabled, users can download the Company Portal app to their device and complete the device enrollment process.

### Enable company-owned device enrollment
You can also enable a variety of [company-owned device enrollment](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) scenarios including:
- [Apple Device Enrollment Program](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Apple Configurator Setup Assistant enrollment](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator Setup Assistant enrollment](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Device Enrollment Manager](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### Next steps
Congratulations! You have just completed the last step of the *Intune quick start guide*. Now that your initial configuration is complete, you can consider enabling additional MDM functionality.

>[!div class="step-by-step"]

>[&larr; **Enroll devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Post-configuration tasks** &rarr;](.\post-configuration-tasks.md)  
