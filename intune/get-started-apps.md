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

The following example steps you through how to add a iOS app in Microsoft Intune.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **Apps** under the **Manage** section.
5. Choose **Add** on the right side of the **Apps** pane.
6. In the **App type** list, select **iOS** under the available **Store app** types.
6. Choose **Search the App Store**.
7. In the **Search the App Store** blade, first select the App store country locale.
8. Type the name (or part of the name) in the search box. Intune searches the store and return a list of relevant results.
9. From the list, choose the app you want, then click **Select**.
10. Select **App information** to configure the app information.
11. (Optional) Add details to help you organize this app, such as **Owner**, **Notes**, **Developer**, and a **Privacy URL** (pointing to your company’s privacy policy).
12. Selected **Yes** for the **Display this as a featured app in the Company Portal** option. 
13. Click **OK** after you have added all of the necessary app information.
14. Click **Add** in the **Add app** blade.This will take you to that app’s **Overview**. 

## Next steps

Now that you have added an app to Intune, you can assign which groups of employees will be able to include the app on their device.

- [How to assign apps to groups](apps-deploy.md)
- 
## Learn more

* [What is app management with Intune?](app-management.md)
* [Overview of the app lifecycle](app-lifecycle.md)
* [What are app protection policies?](app-protection-policy.md)
