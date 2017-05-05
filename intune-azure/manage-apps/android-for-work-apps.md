---
# required metadata

title: Assign apps to Android for Work devices | Microsoft Docs
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Use this topic to synchronize, then assign apps to Android for Work devices from the Google Play for Work Store."
keywords:
author: robstackmsftms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# How to assign apps to Android for Work devices with Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You assign apps to Android for Work devices in a different way than you assign them to standard Android devices. All apps you install for Android for Work come from the Google Play for Work store. You log into the store, browse for the apps you want, and approve them.
The app then appears in the **Licensed apps** node of the Intune portal. From here, you can manage assignment of the app in the same way you would assign any other app.

Additionally, if you have created your own line of business (LOB) apps, you can assign them. To do that, you need to sign up for a Google Developer account which lets you publish apps to a private area in the Google Play store and then synchronize them with Intune.

## Before you start

1. Make sure you have configured Intune and Android for Work to work together in the **Admin** tab of the Intune console.

## Synchronize an app from the Google Play for Work store


1. Go to the [Google Play for Work store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android for Work.
2. Search the store for the app you want to assign using Intune.
3. On the page for the app you chose, choose **Approve**. In this example, you have chosen the Microsoft Excel app.<br>
  ![Approve app example](media/approve.png)
4. A window for the app opens asking you to give permissions for the app to perform various operations. You must choose **Approve** to continue.<br>
  ![Approve app permissions example](media/approve-app-permissions.png)
5. After a moment, you'll see a confirmation message that the app has been approved and is available in your IT admin console.

## Publish, then synchronize, a line of business app from the Google Play for Work store

1. Go to the Google Play Developer Console, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Sign in with the same account you used to configure the connection between Intune and Android for Work. If you are signing in for the first time, you must register, and pay a fee to become a member of the Google Developer program.
3. In the console, choose **Add new application**.
4. You upload and provide information about your app in the same way as you publish any app to the Google Play store. However, you must select the setting **Only make this application available to my organization (<*organization name*>)** as shown below.<br>
  ![Option to only make app available to your organization](media/restrict.png)<br>
This ensures that the app is only available to your organization, and is not available in the public Google Play store.
For more information about how to upload and publish Android apps, see the [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).
5. Once you have published your app, go to the [Google Play for Work store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android for Work.
6. In the **Apps** node of the store, verify you can see the app you have published. Note that it has been automatically approved to be synchronized with Intune.

## Assign an Android for Work app

If you have approved an app from the store and don't yet see it in the **Licensed apps** node of the **Mobile apps** workload, you can force an immediate sync as follows:

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **Setup** > **Android for Work**.
5. On the Android for Work blade, choose **Sync Now**.
6. The page also displays the time and status of the last sync.

When the app is displayed in the **Licensed apps** node of the **Mobile apps** workload, you can [assign it just like you would any other app](/intune-azure/manage-apps/deploy-apps). You can assign the app to groups of users only.

After you assign the app, it will be installed on the devices you targeted. The user of the device will not be asked to approve the installation.

## Manage app permissions
Android for Work requires you approve apps in Google's managed Play web console before syncing them to Intune and assigning them to your users.  Because Android for Work allows you to silently and automatically push these apps to users' devices, you must accept the app's permissions on behalf of all your users.  End users will not see any app permissions when they install, so it's important that you read and understand these permissions.

When an app developer publishes a new version of the app with updated permissions, those permissions are not automatically accepted, even if you've approved the previous permissions. Devices that running the old version of the app can still use it, but the app won't be upgraded until the new permissions are approved. Devices without the app installed cannot install the app until you approve the app's new permissions.

### How to update app permissions

You should periodically visit the managed Google Play console to check for new permissions. If you assign an app and observe it isn't installed on devices, check for new permissions with the following steps:

1. Visit http://play.google.com/work
2. Sign in with the Google account you used to publish and approve the apps.
3. Visit the **Updates** tab to see if any apps require an update.  Any listed apps require new permissions and won't assign until they are applied.  
