---
# required metadata

title: Deploy apps to Android for Work devices | Microsoft Intune
description: Use this topic to synchronize, then deploy Android for Work apps from the Google Play for Work Store.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to deploy Android for Work apps with Intune

Android for Work apps work differently from standard Android Apps. All apps you install for Android for Work come from the Google Play for Work store. You log into the store, select the apps you want, and approve them.
The app then appears in the **Volume-Purchased Apps** node of the Intune console. From here, you can manage deployment of the app in the same way you would deploy any other app.
Additionally, if you have created your own line of business (LOB) app, you can deploy these. To do this, you need to sign up for a Google Developer account. This lets you publish apps to a private area in the Google Play store and then synchronize them with Intune.

## Before you start

1. Make sure you have connected Intune and Android for Work.

## Synchronize an app from the Google Play for Work store


1. Go to the [Google Play for Work store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android for Work.
2. Search the store for the app you want to deploy using Intune.
3. On the page for the app you chose, choose **Approve**. In this example, you have chosen the Microsoft Excel app.

![Approve app example](..\media\approve.png)

4. A window for the app opens asking you to give permissions for the app to perform various operations. You must choose **Approve** to continue.

![Approve app permissions example](..\media\approve-app-permissions.png)

5. After a moment, you'll see a confirmation message that the app has been approved and is available in your IT admin console. 

## Publish, then synchronize, a line of business app from the Google Play for Work store 

1. Go to the Google Play Developer Console, [play.google.com/apps/publish](play.google.com/apps/publish).
2. Sign in with the same account you used to configure the connection between Intune and Android for Work. If you are signing in for the first time, you must register, and pay a fee to become a member of the Google Developer program.
3. In the console, choose **Add new application**.
4. The process to upload and provide information about your app is the same as for publishing any app to the Google Play store. However, you must select the setting **Only make this application available to my organization (<*organization name*>)** as shown below.

![Option to only make app available to your organization](..\media\restrict.png)

This ensures that the app is only available to your organization, and is not available in the public Google Play store.
For more information about how to upload and publish Android apps, see the [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).
5. Once you have published your app, go to the [Google Play for Work store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android for Work. 
6. In the **Apps** node of the store, verify you can see the app you have published. Note that it has been automatically approved to be synchronized with Intune.

## Deploy an Android for Work app

Typically, Intune will synchronize twice a day with the Google Play for Work store. If you have approved an app from the store and don't yet see it in the **Volume-Purchased Apps** node of the **Apps** workspace, you can force an immediate sync as follows:

1. In the [Intune administrator console](https://manage.microsoft.com), choose **Admin** > **Mobile Device Management** > **Android for Work**.
2. On the **Android for Work Mobile Device Management Setup** page, choose **Sync Now**.
3. The page also displays the time and status of the last sync.

When the app is displayed in the **Volume-Purchased Apps** node of the **Apps** workspace, you can [deploy it just like you would any other app](deploy-apps-in-microsoft-intune.md). You can deploy the app to users or devices. Currently, only the deployment action of **Required** and **Uninstall** can be used. 

After you deploy the app, it will be installed on the devices you targeted. The user of the device will not be asked for approval.
