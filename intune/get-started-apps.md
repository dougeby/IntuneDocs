---
# required metadata

title: Getting started with apps in Microsoft Intune
titlesuffix:
description: Find and add apps to devices to make it possible for your workforce to get work done.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
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

# Get started with adding apps in Microsoft Intune

Before you can assign, monitor, configure, or protect apps, you must add them to Intune. Intune supports several different app types. Also, the available options differ for each app type.

Intune lets you add and assign these app types to your corporate devices:
- **Apps from the store** - For devices where you need additional mobile application management applied to apps available in the App Store.
- **Apps written in-house (line-of-business)** - Where you upload a file that is downloaded to your users' devices.
- **Apps that are built in** - Where you assign curated managed apps, such as Office 365 apps, to iOS and Android devices.
- **Apps on the web** - Where Intune creates a shortcut to the web app on the device home screen.

## How do I assign a public store app?

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. Select **Mobile Apps**, then select **Apps**.
4. Select **Add**, then select **iOS** as the **App type**.
5. Choose **Select app** to display the **Search the App Store** pane.
6. In the text box, search for an app to assign to the device. Choose the app, then click **Select**.
7. In the **Add app** pane, select **App information**, then make sure that all of the app information populated. You can add other optional details to help you organize this app, like **Owner**, **Notes**, **Developer**, and a **Privacy URL** for your company’s privacy policy.
8. Make sure that you’ve selected **Yes** for **Display this as a featured app in the Company Portal**, then select **OK**.
9. Select **Add** from the **Add app** pane to add the app. This action takes you to that app’s **Overview**. Choose **Assignments**, then click **Add group** to assign it to your test group. Make the app **Available** for download. The app should then appear as a **Featured App** on your test device.


- [How to assign apps to groups](apps-deploy.md)

## Learn more

* [What is app management with Intune?](app-management.md)
* [Overview of the app lifecycle](app-lifecycle.md)
* [What are app protection policies?](app-protection-policy.md)
