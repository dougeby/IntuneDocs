---
title: include file
description: include file
author: ErikjeMS  
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
---

These notices provide important information that can help you prepare for future Intune changes and features. 


### Decreasing support for Android device administrator 
Android device administrator (sometimes referred to “legacy” Android management and released with Android 2.2) is a way to manage Android devices. However, improved management functionality is now available with [Android Enterprise](../connect-intune-android-enterprise.md) (released with Android 5.0). In an effort to move to modern, richer, and more secure device management, Google is decreasing device administrator support in new Android releases.

#### How does this affect me?
Because of these changes by Google, Intune users will be impacted in the following ways: 
- Intune will only be able to provide support for device administrator-managed Android devices running Android 10 and later (also known as Android Q) through Summer 2020. This date is when the next major version of Android is expected to release.  
- Device administrator-managed devices that are running Android 10 or later after summer 2020 will no longer be able to be entirely managed.    
- Device administrator-managed Android devices that remain on Android versions below Android 10 will not be impacted and can continue to be entirely managed with device administrator.  
- For all Android 10 and later devices, Google has restricted the ability for device administrator management agents like Company Portal to access device identifier information. This impacts the following Intune features after a device updates to Android 10 or later: 
    - Network access control for VPN will no longer work.  
    - Identifying devices as corporate-owned with IMEI or serial number will not automatically mark devices as corporate-owned. 
    - IMEI and serial number will no longer be visible to IT admins in the Intune. 
        > [!Note]
        > This only impacts device administrator-managed devices on Android 10 and later, and does not affect devices being managed as Android Enterprise. 

#### What do I need to do to prepare for this change?
To avoid the reduction in functionality coming in Summer 2020, we recommend the following:
- Don’t onboard new devices into device administrator management.
- If a device is expected to receive an update to Android 10, migrate it off of device administrator management to Android Enterprise management and/or App Protection Policies.

#### Additional information
- [Google’s guidance for migration from device administrator to Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google’s documentation on the plan to deprecate the device administrator API](https://developers.google.com/android/work/device-admin-deprecation)

### Update your Android Company Portal app to the latest version <!--4536963-->
Intune periodically releases updates to the Android Company Portal App. In November 2018 we released a company portal update, which included a back-end switch to prepare for Google’s change from their existing notification platform to Google’s Firebase Cloud Messaging (FCM). When Google retires their existing notification platform and moves to FCM, end users will need to have updated their company portal app to at least November 2018 release to continue communicating with the Google play store.

#### How does this affect me?
Our telemetry indicates you have devices with a Company Portal version earlier than 5.0.4269.0. If this version or later of the company portal app is not installed, IT pro initiated device actions like wipe, reset password, available and required app installs, and certificate enrollment may not work as expected. If your devices are MDM enrolled in Intune, then you can see the company portal versions and users by going to Client apps – Discovered apps. Selecting earlier versions of the Company Portal will allow you to see what end users have the devices that haven’t updated the company portal.

#### What do I need to do to prepare for this change?
Ask end users of Android devices that have not updated to update the company portal through Google play. Notify your help desk in case a user has not kept auto-updating of the company portal app. See the link in Additional Information for more on Google’s FCM platform and change.

#### Additional information
https://firebase.google.com/docs/cloud-messaging/


### New Fullscreen experience coming to Intune <!--4593669-->
We’re rolling out updated create and edit UI experiences to Intune in the Azure portal. This new experience will simplify the existing workflows by using a wizard style format condensed within one blade. This update will do away with “blade sprawl” or any create and edit flows that require you to drill down into deep blade journeys. The create workflows will also be updated to include Assignments (except for App assignment).

#### How does this affect me?
The full screen experience will be rolled out to Intune both at portal.azure.com and devicemanagement.microsoft.com over the next few months. This update to the UI will not impact functionality of your existing policies and profiles, but you will see a slightly modified workflow. When you create new policies, for example, you will be able to set some assignments as part of this flow instead of doing so after creating the policy. See the blog post at Additional information for screenshots of what the new experience will look like in the console.

#### What can I do to prepare for this change?
You do not need to take any action but can consider updating your IT pro guidance if necessary. We’ll update our documentation as this experience rolls out to various blades in the Intune on Azure portal.

#### Additional information 
https://aka.ms/intune_fullscreen

### Plan for change: New Windows updates settings in Intune <!-- 4464404 -->
Starting with the August release to the Intune service or 1908, we’re adding in new “Deadline settings”, which you can configure instead of the “Allow user to restart (engaged restart)” settings. We plan to disable the engaged restart settings in the UI in 1909 or the September update and then completely remove them from the console towards the end of October. 

#### How does this affect me?
If you manage Windows 10 devices in your environment: 
- With the August Intune update or 1908, you will see new deadline settings in the console in addition to the old engaged restart settings.
- When both these old and new settings are configured, the deadline settings values will override the engaged restart setting values.
- Deadline settings will replace the “Allow user to restart (engaged restart) option in the console in the 1910 update.

#### What can I do to prepare for this change?
Start using the deadline settings in 1908 by configuring them with your desired values. Once you have that in place, you can set the engaged restart setting to “Not configured” to prepare for these settings being removed from the console in October.

Update your documentation and any automation scripts if needed. 

We’ll keep you updated and post a reminder to the Message center before we remove the engaged restart settings.

### Plan for change: Intune App SDK and app protection policies for Android moving to support Android 5.0 and higher in October <!--4911065 -->
Intune will be moving to support Android 5.x (Lollipop) and higher in October. Update any wrapped apps with the latest Intune App SDK and update your devices.

#### How does this affect me?
If you’re not using or plan to use either the SDK or APP for Android, this change won’t affect you. If you are using the Intune App SDK, be sure to update to the latest version and also update your devices to Android 5.x and higher. If you don’t update, apps will not receive updates, and the quality of their experience will diminish over time. 

Below find a list of common devices enrolled in Intune that run Android version 4.x. If you have one of these devices,  take the appropriate steps to make sure that this device will support Android version 5.0 or higher or that it will be replaced with a device that supports Android version 5.0 or higher. This list is not exhaustive of all devices that may need to be evaluated:
- Samsung SM-T561  
- Samsung SM-T365 
- Samsung GT-I9195 
- Samsung SM-G800F
- Samsung SM-G357FZ
- Motorola XT1080
- Samsung GT-I9305
- Samsung SM-T231

#### What do I need to do to prepare for this change?
Wrap your apps with the latest Intune App SDK. You may also set the “Require minimum OS  version (Warning only)” conditional launch setting to notify end-users on personal devices to upgrade.


### Intune plan for change: nearing end of support for Windows 7 <!-- 3042987 -->
As we messaged in MC148476 posted last September 2018, and again in MC176794 back in March 2019, Windows 7 reaches end of extended support on January 14, 2020. At that time, Intune will retire support for devices running Windows 7, so we can focus our investment on supporting newer technologies and providing great new end user experiences. After that date, technical assistance and automatic updates that help protect your Windows 7 PC will no longer be available through Intune. Microsoft strongly recommends that you move to Windows 10 before January 2020, to avoid a scenario where you need service or support that is no longer available. Read more about the Windows support lifecycle [here](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### How does this affect me?
You are receiving this message because you are currently managing Windows 7 PC's using the legacy Intune PC software agent. With less than a year remaining before the end of Windows 7 extended support, we strongly encourage your organization to begin upgrading to Windows 10 as soon as possible. 
PC management capabilities are built directly into the Windows 10 operating system, and you no longer need to install a client agent such as the Intune Software Client for Windows 7. Starting with Windows 8.1, Microsoft uses the Mobile Device Management (MDM) architecture to provision, configure, update, and manage Windows PCs. Once you have set up Intune, you can simplify Windows enrollment by [enrolling Windows 10 PCs into Intune](..\windows-enroll.md) through the MDM channel. We recommend that you use this “agentless” MDM management solution to manage your Windows 10 PC’s.

#### What do I need to do to prepare for this change?
We encourage your organization to immediately consider this action plan:

- Plan and upgrade the Windows 7 fleet to Windows 10 before January 14, 2020.
- Explore [Windows 10 deployment support](https://docs.microsoft.com/windows/deployment/) to learn more on how to upgrade your existing fleet of Windows 7 PC's to Windows 10.
- Review the [Desktop App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) offer through Fast Track who will assist with Microsoft’s application compatibility promise.
- Transition existing legacy Intune Software Client managed devices to the Microsoft recommended solution to manage Windows 10 using MDM management. Enroll all new Windows 10 PC's using MDM management for Intune in the Azure portal.
- See the [blog posted here](https://aka.ms/Windows7_Intune) for more information.
