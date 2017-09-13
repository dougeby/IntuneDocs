---
# required metadata

title: Getting started with apps
titlesuffix: "Azure portal"
description: Find and add apps to devices to make it possible for your employees to get work done.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Get started with adding apps

Intune supports a few different ways for you to deploy apps to your corporate devices:

* **Software installers**: where you upload a file that is downloaded to your users' devices
* __External links__: for when you have an app in a public app store or a webapp
* **Managed apps**: for iOS devices where you need additional mobile application management applied to apps available in the App Store

You’re going to go through one of the quicker application deployment methods by assigning a public store app.

## How do I assign a public store app?

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Using **Search resources**, search for **Intune**.
3. Select **Mobile Apps**, then select **Apps**.
4. Select **Add**, then **iOS store app** as the **App type**.
5. In the text box, search for an app to assign to the device. Choose the app, then select **OK**.
6. In the **Add app** blade, select **App information**, then make sure that all of the app information populated. You can add other optional details to help you organize this app, like **Owner**, **Notes**, **Developer**, and a **Privacy URL** for your company’s privacy policy.
7. Make sure that you’ve selected Yes for Display this as a featured app in the Company Portal, then select OK.
8. Select **Add** to add the app. This will take you to that app’s **Overview**. Choose **Assignments**, then click **Select groups** to assign it to your test group. Make the app **Available** for download. The app should then appear as a **Featured App** on your test device.

## Learn more

* [What is app management with Intune?](app-management.md)
* [Overview of the app lifecycle](app-lifecycle.md)
* [What are app protection policies?](app-protection-policy.md)
