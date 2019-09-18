---
# required metadata

title: Assign Managed Google Play apps to Android Enterprise devices
titleSuffix: Microsoft Intune
description: Understand how to synchronize and assign apps to Android Enterprise devices from the Managed Google Play store.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic
ms.collection: M365-identity-device-management
---

# Add Managed Google Play apps to Android Enterprise devices with Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Enterprise is a program for Android work profile devices, dedicated/kiosk devices, and fully managed devices. For Android work profile devices, Android Enterprise is a set of features and services that separate personal apps and data from work apps and data. Android Enterprise provides additional management options and privacy when people use their Android devices for work. Intune helps you deploy apps and settings to Android work profile devices to make sure work and personal information are separate. All apps you install on Android work profile devices come from the Managed Google Play store. How you assign apps to Android work profile devices differs from how you assign them to standard Android devices. You sign in to the store, browse for the apps you want, and approve them. The app then appears in the **Licensed apps** node of the Azure portal, and you can manage assignment of the app as you would any other app.

Additionally, if you have created your own line-of-business (LOB) apps, you can assign them as follows:
- Sign up for a Google Developer account that lets you publish apps to a private area in the Google Play store.
- Synchronize the apps with Intune.

To make it easier for you to configure and use Android Enterprise management, upon connecting to Google Play, Intune will automatically add four common Android Enterprise related apps to the Intune admin console. The four Android Enterprise apps are the following:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** - Used for Android Enterprise fully managed scenarios.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** - Helps you sign-in to your accounts if you use two-factor verification.
- **[Intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** - Used for App Protection Policies (APP) and Android Enterprise work profile scenarios.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) - Used for Android Enterprise dedicated/kiosk scenarios.

>[!NOTE]
>When an end user enrolls their Android Enterprise fully managed device, the Intune Company Portal app is automatically installed and the application icon may be visible to the end user. If the end user attempts to launch the Intune Company Portal app, the end user will be redirected to the Microsoft Intune app and the Company Portal app icon will be subsequently hidden.

## Before you start

Make sure you have configured Intune and Android work profiles to work together in the **Device enrollment** workload of the Azure portal. For more information, see [Enroll Android devices](android-work-profile-enroll.md).

>[!NOTE]
>When you work with Microsoft Intune, we recommend that you use either the Microsoft Edge or Google Chrome browser.

## Managed Google Play app type
The **managed Google Play** app type will allow you to specifically add [Managed Google Play apps](https://play.google.com/work/search?q=microsoft&c=apps) to Intune. As the Intune admin, you can now browse, search, approve, sync, and assign approved managed Google Play apps within Intune.  You no longer need to browse to the managed Google Play console separately, and you no longer have to reauthenticate.

> [!NOTE]
> If you prefer to synchronize a Managed Google Play app with Intune, see [Synchronize a Managed Google Play app with Intune](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## Add a Managed Google Play app using Intune

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. In the **Intune** pane, select **Client apps** > **Apps**.
5. In the **Apps** pane, select **Add**.
6. In the **App type** dropdown box, select **Managed Google Play**.
7. Select **Managed Google Play - Approve** to open the managed Google Play catalog.
8. Use the search box to search for apps that you want to include.
9. Click **Approve** to approve the app in managed Google Play and click **Approve** to accept the app permissions.
10. Select **Keep approved when app requests new permissions** in the Approval Settings window and then click **Save**. If you do not choose this option, you will need to manually approve any new permissions if the app developer publishes an update. This will cause installations and updates of the app to stop until permissions are approved. For this reason, it is recommended to select the option to automatically approve new permissions. 
11. Click **OK** to include the app(s) you have approved.
12. Click **Sync** on the **App app** pane to sync with the Managed Google Play service.

## Synchronize a Managed Google Play app with Intune (Alternative)
If you prefer to synchronize a Managed Google Play app with Intune rather than adding it directly using Intune, use the following steps.

> [!IMPORTANT]
> The information provided below is an alternative method to adding a Managed Google Play app using Intune as described above.

### Synchronize an app from the Managed Google Play store

1. Go to the [Managed Google Play store](https://play.google.com/work). Sign in with the same account you used to configure the connection between Intune and Android Enterprise.
2. Search the store and select the app you want to assign by using Intune.
3. On the page that displays the app, select **Approve**.  
    In the following example, the Microsoft Excel app has been chosen.

    ![The Approve button in the Managed Google Play store](media/approve.png)

   A window for the app opens asking you to give permissions for the app to perform various operations.

4. Select **Approve** to accept the app permissions and continue.

    ![The Approve button for app permissions](media/approve-app-permissions.png)

5. Select an option for handling new app permission requests, and then select **Save**.

    ![Options for handling new app permission requests](media/approve-app-settings.png)

    The app is approved, and it is displayed in your IT admin console. Next, you can [sync the Android work profile app with Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

### Sync a Managed Google Play app with Intune

If you have approved an app from the store and don't see it in the **Licensed apps** node of the **Client apps** workload, force an immediate sync as follows:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. In the **Intune** pane, select **Client apps**.
4. In the **Client apps** workload pane, under **Setup**, select **Managed Google Play**.
5. In the **Managed Google Play** pane, choose **Refresh**.  
    The page updates the time and status of the last sync.
6. In the **Client apps** workload pane, select **Apps**.  
    The newly available Managed Google Play app is displayed.

## Assigning a Managed Google Play app to Android Enterprise work profile devices

When the app is displayed in the **App licenses** node of the **Client apps** workload pane, you can [assign it just as you would assign any other app](/intune-azure/manage-apps/deploy-apps) by assigning the app to groups of users.

After you assign the app, it is installed (or available for install) on the devices of the users that you've targeted. The user of the device is not asked to approve the installation. For more information about Android Enterprise work profile devices, see [Set up enrollment of Android Enterprise work profile devices](android-work-profile-enroll.md). 

> [!NOTE] 
> Only apps that have been assigned will show up in the Managed Google Play store for an end user. As such, this is a key step for the admin to take when setting up apps with Managed Google Play.

## Assigning a Managed Google Play app to Android Enterprise fully managed devices

[Android Enterprise fully managed devices](android-fully-managed-enroll.md) are corporate-owned devices associated with a single user and used exclusively for work and not personal use. Users on fully managed devices can get their available company apps from the managed Google Play app on their device.

By default, an Android Enterprise fully managed device will not allow employees to install any apps that are not approved by the organization. Also, employees will not be able to remove any installed apps against policy. If you wish to allow users to access the full Google Play store to install apps rather than only having access to the approved apps in Managed Google Play store, you can set the **Allow access to all apps in Google Play store** to **Allow**. With this setting, the user can access all the apps in the Google Play store using their corporate account, however purchases may limited. You can remove the limited purchases restriction by allowing users to add new accounts to the device. Doing so will enable end users to have the ability to purchase apps from the Google Play store using personal accounts, as well as conduct in-app purchases. For more information, see [Android Enterprise device settings to allow or restrict features using Intune](device-restrictions-android-for-work.md). 

> [!NOTE]
> The Microsoft Intune app and the Microsoft Authenticator app will be installed as required apps onto all fully managed devices during onboarding. Having these apps automatically installed provides Conditional Access support, and Microsoft Intune app users can see and resolve compliance issues. 

## Manage Android Enterprise app permissions
Android Enterprise requires you to approve apps in the managed Google Play web console before you sync them with Intune and assign them to your users. Because Android Enterprise allows you to silently and automatically push the apps to users' devices, you must accept the app permissions on behalf of all your users. Users don't see any app permissions when they install the apps, so it's important that you understand the permissions.

When an app developer updates permissions with a new version of the app, the permissions are not automatically accepted even if you approved the previous permissions. Devices that run the previous version of the app can still use it. However, the app is not upgraded until the new permissions are approved. Devices without the app installed do not install the app until you approve the app's new permissions. 

### Update app permissions

Periodically visit the managed Google Play console to check for new permissions. You can configure Google Play to send you or others an email when new permissions are required for an approved app. If you assign an app and observe that it isn't installed on devices, check for new permissions following these steps:

1. Go to [Google Play](https://play.google.com/work).
2. Sign in with the Google account that you used to publish and approve the apps.
3. Select the **Updates** tab, and check to see whether any apps require an update.  
    Any listed apps require new permissions and are not assigned until they are applied.

Alternatively, you can configure Google Play to automatically reapprove app permissions on a per-app basis.

## Additional Managed Google Play app reporting for Android Enterprise work profile devices

For Managed Google Play apps deployed to Android Enterprise work profile devices, you can view the specific version number of the app installed on a device. This applies to required apps only. 

## Working with a line-of-business app from the Managed Google Play store

1. Sign in to the [Google Play Developer Console](https://play.google.com/apps/publish) with the same account you used to configure the connection between Intune and Android Enterprise.  
    If you are signing in for the first time, you must register and pay a fee to become a member of the Google Developer program.
2. In the console, select **Add new application**.
3. You upload and provide information about your app in the same way as you publish any app to the Google Play store. However, you must select **Only make this application available to my organization (<*organization name*>)**.

    ![Make the app available only to your organization](media/restrict.png)

    This operation makes the app available only to your organization. It won't be available on the public Google Play store.

    For more information about uploading and publishing Android apps, see [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).
4. After you've published your app, sign in to the [Managed Google Play store](https://play.google.com/work) with the same account that you used to configure the connection between Intune and Android Enterprise.
5. In the **Apps** node of the store, verify that the app you've published is displayed.  
    The app is automatically approved to be synchronized with Intune.

## Delete Managed Google Play apps
When necessary, you can delete managed Google Play apps from Microsoft Intune. To delete a managed Google Play app, open Microsoft Intune in the Azure portal and select **Client apps** > **Apps**. From the app list, select the ellipses (...) to the right of the managed Google Play app, then select **Delete** from the displayed list. When you delete a managed Google Play app from the app list, the managed Google Play app is automatically unapproved.

## Android Enterprise system apps

You can enable an Android Enterprise system app for [Android Enterprise dedicated devices](android-kiosk-enroll.md) or [fully managed devices](android-fully-managed-enroll.md). For more information about adding an Android Enterprise system app, see [Add Android Enterprise system apps to Microsoft Intune](apps-ae-system.md).

## Next steps

- [Assign apps to groups](apps-deploy.md)
