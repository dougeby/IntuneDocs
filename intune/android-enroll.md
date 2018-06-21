---
# required metadata

title: Enroll Android devices in Intune
titlesuffix: "Microsoft Intune"
description: Learn how to enroll Android devices in Intune.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll Android devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As an Intune administrator, you can manage Android devices, including Samsung Knox Standard devices. You can also manage [Android work profile devices](#enable-enrollment-of-android-for-work-devices).

Devices that run Samsung Knox Standard are supported for multi-user management by Intune. This means that users can sign in and out of a device with their Azure AD credentials. The device is centrally managed whether it’s in use or not. When users sign in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.

## Prerequisite

To prepare to manage mobile devices, you must set the mobile device management (MDM) authority to **Microsoft Intune**. See [Set the MDM authority](mdm-authority-set.md) for instructions. You set this item only once, when you are first setting up Intune for mobile device management.

## Set up Android enrollment

By default, Intune allows enrollment of Android and Samsung Knox Standard devices.

To block Android devices, or to block only personally owned Android devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).

To enable device management, your users must enroll their devices by downloading the Intune Company Portal app (available from Google Play), and then opening the app and following the prompts. After Android devices are managed, you [assign compliance policies](compliance-policy-create-android.md), [manage apps](app-management.md), and more.

## Enable enrollment of Android work profile devices

Android enterprise is a set of Android device features and services that separate personal apps and data from a work profile containing work apps and data. Android enterprise provides additional management capabilities and privacy when people use their Android work profile devices for work. Intune helps you deploy apps and company resources to Android work profile devices to ensure work and personal information is separate. When successfully deployed, apps and the data they access remain exclusively within the Android enterprise environment on the device. For specific details about Android enterprise, see [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

To enable management of the work profile on devices that [support Android work profiles](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), you must add an Android  binding to Intune. If you want to enroll devices in Android work profiles, but those devices were already enrolled as regular Android devices, you must unenroll the devices and then re-enroll them.

If you're enrolling Android work profile devices by using a [Device Enrollment Manager](device-enrollment-manager-enroll.md) account, there is a limit of 10 devices that can be enrolled per account.

For more information, see [Data Intune sends to Google](data-intune-sends-to-google.md).

## Add Android enterprise binding for Intune

You must establish a binding between your Intune tenant and Google’s Play for Work service, which is an integral part of the Android enterprise app distribution and management process. 

> [!NOTE]
> Due to interaction between Google and Microsoft domains, this step may require that you adjust your browser settings in order to successfully complete.  Make sure that "portal.azure.com" and "play.google.com" are in the same security zone in your browser.

1. **Set up Intune MDM**<br>
If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](mdm-authority-set.md) as **Microsoft Intune**.
2. **Configure Android enterprise binding**<br>
    
   a. Sign in to the [Intune in the Azure portal](https://aka.ms/intuneportal), select **Device enrollment** > **Android enrollment** > **Managed Google Play**.  If you are using a custom Intune admin role, access to this requires Organization Read and Update permissions.
   
   ![Android enterprise enrollment screen](./media/android-work-bind.png)

   b. Select **I agree** to grant Microsoft permission to [send user and device information to Google](data-intune-sends-to-google.md). 
   
   c. Select **Launch Google to connect now** to open the Managed Google Play website. The website opens on a new tab in your browser.
  
   d. **Sign in to Google**<br>
   On Google's sign-in page, enter the Google account that will be associated with all Android enterprise management tasks for this tenant. This is the Google account that your company's IT admins share to manage and publish apps in the Google Play console. You can use an existing Google account or create a new one.  The account you choose must not be associated with a G-Suite domain.
    
    > [!Note]
    > If you are using the Microsoft Edge browser, click **Sign-In** in the upper right corner to sign-in to your Google account.

   e. **Provide organization details**<br>
   Provide your company's name for **Organization name**. For **Enterprise mobility management (EMM) provider**, **Microsoft Intune** should be displayed. Agree to the Android agreement, and then choose **Confirm**. Your request will be processed.

## Specify Android work profile enrollment settings
Android work profiles are supported on only certain Android devices. See Google's [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Any device that supports Android work profiles also supports conventional Android management. Intune lets you specify how devices that support Android work profiles should be managed from within [Enrollment Restrictions](enrollment-restrictions-set.md).

- **Block (set by default)**:  All Android devices, including devices that support Android work profiles, will be enrolled as conventional Android devices.
- **Allow**: All devices that support Android work profiles are enrolled as Android work profile devices. Any Android device that does not support Android work profiles is enrolled as a conventional Android device.

## Approve the Company Portal app in the managed Google Play store
You must approve the Company Portal app for Android in the managed Google Play store to ensure that it receives automatic app updates. If you don't approve it, the Company Portal will eventually become out of date and may not receive important bug fixes or new features when Microsoft releases them.

Follow these steps to approve the Intune Company Portal:

1.  Browse to the Company Portal app on the [managed Google Play store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Sign into the managed Google Play store with the same Google account that you used to configure the binding for Android enterprise.
3.  Click **Approve** and a new dialog will open.
4.  Review the permissions in this dialog, then click **Approve**. You need these to allow these permissions in order to allow the Company Portal app to manage the work profile on the device.
5.  Select **Keep approved when app requests new permissions**, then click **Save.**

<!--  ## Next steps for Android work profiles
After configuring the Android enterprise binding and settings, you can do the following:
- [Deploy Android work profile apps](android-for-work-apps.md)
- [Add Android work profile configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## Tell your users how to enroll their devices to access company resources

Tell your users to go to Google Play to download the Intune Company Portal app, and then open the app and follow the prompts to enroll their device. The app guides users through the enrollment process, explaining what users can expect and what IT administrators can and can't see on their devices.

You can also send them a link to online enrollment steps: [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

For information about other user tasks, see these articles:

- [Resources about the end-user experience with Microsoft Intune](end-user-educate.md)
- [Using your Android device with Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## Unbind your Android enterprise administrative account

You can turn off Android enterprise enrollment and management. Choosing **Unbind** in the Intune administration console removes all enrolled Android work profile devices from enrollment. It also removes the relationship between the Android enterprise account and Intune.

### To unbind an Android enterprise account

1. **Unbind Android enterprise binding**<br>
    As an Intune administrator, in the [Azure portal](https://portal.azure.com), choose **All Services** > **Monitoring + Management** > **Intune**.  On the **Intune** pane, choose **Device enrollment**, > **Android for Work Enrollment**, and then choose **Unbind**.

2. **Agree to delete Android for Work binding**<br>
  Choose **Yes** to delete the binding and unenroll all Android work profile devices from Intune.

## End user experience when enrolling a Samsung Knox device
There are several considerations when enrolling Samsung Knox devices:
-	Even if no policies require a PIN, the device must have at least a four digit PIN to enroll. If the device does not have a PIN, the user will be prompted to create one.
-	There is no user interaction for Workplace Join Certificates (WPJ).
-	The user is prompted with Service Enrollment info and what the app can do.
-	The user is prompted with Knox Enrollment info and what Knox can do.
-	If an Encryption Policy is enforced, users are required to set a six Character Complex password for the device passcode.
-	There are no additional user prompts to install certificates pushed by a service for Company Resource Access.
- Some older Knox devices will prompt the user for additional certificates used for Company Resource Access.
- If a Samsung Mini device fails to install the WPJ with either the **Certificate Not Found** or **Unable to Register Device** errors, install the latest Samsung Firmware Updates.
