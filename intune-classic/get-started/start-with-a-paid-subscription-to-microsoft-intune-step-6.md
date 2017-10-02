---
# required metadata

title: Deploy policies and apps 
description: You can enable policy settings and deploy apps that will be applied as soon as devices are enrolled into management.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
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
ms.custom: intune-classic

---

# Create policies and publish apps

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic tells Intune administrators how they can create policies and publish apps that they can then deploy to managed devices.

Before you start enrolling apps into Intune, you can enable policy settings and apps that will be deployed as soon as those devices come into management. Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. You can configure policy, add apps, and deploy those apps so that devices receive settings and apps as soon as they enroll in Intune.

Policies and apps are platform-specific.

## Manage device settings

 Device policy settings are configured and managed on a per-platform basis. The following links provide lists of available settings for their respective platforms:

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android and Samsung KNOX Standard](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10  (PC and mobile)](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Windows PCs running Intune software client](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

You can learn more about how to [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## Add and deploy apps

You can add apps to Intune and then deploy them to managed devices in two ways:
- **Required install** - Apps automatically installs the app to managed devices
- **Available install** - Apps appear in the Intune Company Portal so that users can choose whether to install them on their devices

### Add apps

First you must make apps available in Intune by one of the following methods:
- [Add apps for enrolled devices](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Add apps for Intune software client PCs](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### Deploy apps

Now that the app is availabile in Intune, you can deploy it to managed devices:
- [Deploy apps to devices](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Deploy volume-purchased apps:
	- [iOS - Volume-purchase Program](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
	- [Microsoft Store for Business](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
	- [Android for Work](/intune-classic/deploy-use/android-for-work-apps)

	Once you have configured apps for deployment you can [configure apps](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;](/intune/company-portal-customize)  
