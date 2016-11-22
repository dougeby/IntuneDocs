---
# required metadata

title: Deploy policies and apps | Microsoft Intune
description: You can enable policy settings and deploy apps that will be applied as soon as devices are enrolled into management.
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Create policies and publish apps
Before you start enrolling apps into Intune, you can enable policy settings and apps that will be deployed as soon as those devices come into management. Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. You can configure policy, add apps, and deploy those apps so that devices receive settings and apps as soon as they enroll in Intune.

Policies and apps are platform-specific.

## Manage device settings

 Device policy settings are configured and managed on a per-platform basis. You can configure policy for the following platforms:

- [iOS](ios-policy-settings-in-microsoft-intune.md)
- [Android and Samsung KNOX Standard](android-policy-settings-in-microsoft-intune.md)
- [Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)
- [Windows 10 (PC and mobile)](windows-10-policy-settings-in-microsoft-intune.md)
- [Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
- [Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
- [Windows Team](windows-team-configuration-policy-settings-in-microsoft-intune.md)
- [Windows PCs running Intune software client](policies-to-protect-windows-pcs-in-microsoft-intune.md)

You can learn more about how to [Manage settings and features on your devices with Microsoft Intune policies](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## Add and deploy apps

You can add apps to Intune and then deploy them to managed devices in two ways:
- **Required install** - Apps automatically installs the app to managed devices
- **Available install** - Apps appear in the Intune Company Portal so that users can choose whether to install them on their devices

### Add apps

First you must make apps available in Intune by one of the following methods:
- [Add apps for enrolled devices](add-apps-for-mobile-devices-in-microsoft-intune.md)
- [Add apps for Intune software client PCs](add-apps-for-windows-pcs-in-microsoft-intune.md)

### Deploy apps

Now that the app is availabile in Intune, you can deploy it to managed devices:
- [Deploy apps to devices](deploy-apps-in-microsoft-intune.md)
- Deploy volume-purchased apps:
	- [iOS - Volume-purchase Program](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md)
	- [Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md)
	- [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps.md)

	Once you have configured apps for deployment you can [configure apps](update-apps-using-microsoft-intune.md) and [monitor apps](monitor-apps-in-microsoft-intune.md).


### Next steps
Congratulations! You have just completed step 6 of the *Intune quick start guide*.

>[!div class="step-by-step"]

>[&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  
