---
# required metadata

title: Assign apps to Android work profile devices 
titlesuffix: Microsoft Intune
description: Understand how to synchronize and assign apps to Android work profile devices from the Managed Google Play store.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/15/2018
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

# Assign apps to Android work profile devices with Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android enterprise is a program for Android work profile devices and kiosk devices. For Android work profile devices, Android enterprise is a set of Android device features and services that separate personal apps and data from a work profile containing work apps and data. Android enterprise provides additional management capabilities and privacy when people use their Android devices for work. Intune helps you deploy apps and company resources to Android work profile devices to ensure work and personal information is separate. When successfully deployed, apps and the data they access remain exclusively within the Android enterprise environment on the device. All apps you install on Android work profile devices come from the Managed Google Play store. How you assign apps to Android work profile devices differs from how you assign them to standard Android devices. You sign in to the store, browse for the apps you want, and approve them. The app then appears in the **Licensed apps** node of the Azure portal, and you can manage assignment of the app as you would any other app.

Additionally, if you have created your own line-of-business (LOB) apps, you can assign them as follows:
- Sign up for a Google Developer account that lets you publish apps to a private area in the Google Play store.
- Synchronize the apps with Intune.

## Before you start

Make sure you have configured Intune and Android work profiles to work together in the **Device enrollment** workload of the Azure portal. For more information, see [Enroll Android devices](android-work-profile-enroll.md).

## Synchronize an app from the Managed Google Play store

1. Go to the [Managed Google Play store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android enterprise.
2. Search the store and select the app you want to assign by using Intune.
3. On the page that displays the app, select **Approve**.  
    In the following example, the Microsoft Excel app has been chosen.

    ![The Approve button in the Managed Google Play store](media/approve.png)
    
   A window for the app opens asking you to give permissions for the app to perform various operations. 

4. Select **Approve** to accept the app permissions and continue.

    ![The Approve button for app permissions](media/approve-app-permissions.png)

5. Select an option for handling new app permission requests, and then select **Save**.

    ![Options for handling new app permission requests](media/approve-app-settings.png)

    The app is approved, and it is displayed in your IT admin console. Next, you can [sync the Android work profile app with Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## Sync an Managed Google Play app with Intune

If you have approved an app from the store and don't see it in the **Licensed apps** node of the **Mobile apps** workload, force an immediate sync as follows:

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. In the **Intune** pane, select **Mobile apps**.
4. In the **Mobile apps** workload pane, under **Setup**, select **Managed Google Play**.
5. In the **Managed Google Play** pane, choose **Refresh**.  
    The page updates the time and status of the last sync.
6. In the **Mobile apps** workload pane, select **Apps**.  
    The newly available Managed Google Play app is displayed.

When the app is displayed in the **App licenses** node of the **Mobile apps** workload pane, you can [assign it just as you would assign any other app](/intune-azure/manage-apps/deploy-apps). You can assign the app to groups of users only.

After you assign the app, it is installed on the devices that you've targeted. The user of the device is not asked to approve the installation.

## Manage Android enterprise app permissions
Android enterprise requires you to approve apps in the managed Google Play web console before you sync them with Intune and assign them to your users. Because Android enterprise allows you to silently and automatically push the apps to users' devices, you must accept the app permissions on behalf of all your users. Users do not see any app permissions when they install the apps, so it's important that you read and understand the permissions.

When an app developer publishes a new version of the app with updated permissions, the permissions are not automatically accepted, even if you've approved the previous permissions. Devices that run the previous version of the app can still use it. However, the app is not upgraded until the new permissions are approved. Devices without the app installed do not install the app until you approve the app's new permissions.

### Update app permissions

Periodically visit the managed Google Play console to check for new permissions. You can configure Google Play to send you or others an email when new permissions are required for an approved app. If you assign an app and observe that it isn't installed on devices, check for new permissions by doing the following:

1. Go to [Google Play](http://play.google.com/work).
2. Sign in with the Google account that you used to publish and approve the apps.
3. Select the **Updates** tab, and check to see whether any apps require an update.  
    Any listed apps require new permissions and are not assigned until they are applied.

Alternatively, you can configure Google Play to automatically reapprove app permissions on a per-app basis. 

## Working with a line-of-business app from the Managed Google Play store

1. Sign in to the [Google Play Developer Console](https://play.google.com/apps/publish) with the same account you used to configure the connection between Intune and Android enterprise.  
    If you are signing in for the first time, you must register and pay a fee to become a member of the Google Developer program.
2. In the console, select **Add new application**.
3. You upload and provide information about your app in the same way as you publish any app to the Google Play store. However, you must select **Only make this application available to my organization (<*organization name*>)**.

    ![Make the app available only to your organization](media/restrict.png)

    This operation ensures that the app is available only to your organization, and it is not available on the public Google Play store.

    For more information about uploading and publishing Android apps, see [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).
4. After you've published your app, sign in to the [Managed Google Play store](https://play.google.com/work) with the same account that you used to configure the connection between Intune and Android enterprise.
5. In the **Apps** node of the store, verify that the app you've published is displayed.  
    The app is automatically approved to be synchronized with Intune.

## Next steps

- [Assign apps to groups](apps-deploy.md) 

