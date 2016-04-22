---
# required metadata

title: Overview of the app lifecycle | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Overview of the app lifecycle

The Intune app lifecycle begins when an app is added and progresses through additional phases until you remove them.

![The app lifecycle](./media/applifecycle_nobg.png "the Intune app lifecycle")

## Add

The first step in app deployment is to add the apps you want to manage and deploy into Intune. While there are many different app types you can work with, the basic procedures are the same. Intune lets you add apps for both [enrolled devices](add-apps-for-mobile-devices-in-microsoft-intune.md), and [Windows PCs you manage with the Intune client software](create-apps-for-windows-pcs-in-microsoft-intune.md).

## Deploy

Once you've added the app to Intune, you can then [deploy it to devices that you manage](deploy-apps-in-microsoft-intune.md). Intune makes this process easy, and once the app is deployed, you can [monitor the success](monitor-apps-in-microsoft-intune.md) of the deployment from the Intune administration console. Additionally, some app stores, like the  [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) and [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) app stores, allow you to purchase app licenses in bulk for your company. Intune can synchronize data with these stores to let you deploy and track license usage for these types of apps right from the Intune administration console.

## Configure

As part of the app lifecycle, new versions of apps are regularly released. Intune provides tools to easily [update apps](update-apps-using-microsoft-intune.md) you have deployed to a newer version. Additionally, some apps let you configure extra functionality, for example:
- [iOS app configuration policies](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) let you supply settings for compatible iOS apps that are used when the app is run. For example, an app might require specific branding settings or the name of a server to connect to.
- [Managed browser policies](manage-internet-access-using-managed-browser-policies.md) help you to configure settings for the Intune managed browser which replaces the default device browser and lets you restrict the websites that your users can visit.

## Protect

Intune gives you many ways to help protect the data in your apps. The main methods are:
- [Conditional access](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) lets you control access to email and other services based on conditions you specify like device types, or compliance with a [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) you deployed.
- [Mobile application management (MAM)](introduction-to-mobile-app-management-policies-with-microsoft-intune.md) works with individual apps to help protect the company data they use. For example, you can restrict copying data between unmanaged apps and apps you manage, or you can prevent apps from running on devices that have been jailbroken or rooted.

## Retire

Eventually, it's likely that apps you deployed become outdated, and need to be removed. Intune makes it easy to [retire apps from service](retire-apps-using-microsoft-intune.md).
