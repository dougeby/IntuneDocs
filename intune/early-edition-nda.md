---
# required metadata

title: Early edition - Microsoft Intune
titlesuffix: 
description: Microsoft Intune early edition
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
---

# The early edition for Microsoft Intune - January 2019

> [!Note]
> NDA notification: The following changes are under development for Intune. This information is shared under NDA on a very limited basis. Do not post any of this information on social media or public websites such as Twitter, UserVoice, Reddit, and so on. 

The **early edition** provides a list of features, shared under NDA, that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not tweet, post on UserVoice, or otherwise share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal

<!-- 1901 start -->

### Android Enterprise apps <!-- 1352553  -->
You will be able to delete managed Google Play apps from Microsoft Intune. To delete a managed Google Play app, you will open Microsoft Intune in the Azure portal and select **Client apps** > **Apps**. From the app list, you will select the ellipses (...) to the right of the managed Google Play app, then select **Delete** from the displayed list. When you delete a managed Google Play app from the app list, the managed Google Play app is automatically unapproved.

### Managed Google Play app type <!-- 1352580 -->
The **managed Google Play** app type will allow you to specifically add [managed Google Play apps](https://play.google.com/work/search?q=microsoft&c=apps) to Intune. As the Intune admin, you will be able to now browse, search, approve, sync and assign approved managed Google Play apps within Intune. You will no longer need to browse to the managed Google Play console separately, and you will no longer have to reauthenticate. In Intune, select **Client apps** > **Apps** > **Add**. In the **App type** list, select **Managed Google Play** as the app type.

### Preview of support for Android corporate-owned, fully managed devices <!-- 1574342  -->
Intune will support fully managed Android devices, a corporate-owned "device owner" scenario where devices are tightly managed by IT and are affiliated with individual users. This allows admins to manage the entire device, enforce an extended range of policy controls unavailable to work profiles, and restricts users to installing apps from managed Google Play only. To set up Android fully managed devices, you will go to **Device enrollment** > **Android enrollment** > **Corporate-owned, fully managed user devices**. Please note that this feature is in preview. Some Intune capabilities, such as certificates, compliance, and Conditional Access, are not currently available with Android fully managed user devices.

### Deployment of online licensed Microsoft Store for Business apps <!-- 1672660  -->
You will be able to assign required online licensed Microsoft Store for Business apps in the device context. Deploying a Microsoft Store for Business app this way will enable the app to be installed for all users on the device. This is only applicable on Windows 10 RS4+ desktop devices. The option to install in the device context is available in the Client Apps assignment page for MSFB Online Licensed apps.

### Configure profile to skip some screens during Setup Assistant <!-- 2276470  -->
When you create a macOS enrollment profile, you will be able to configure it to skip any of the following screens when a user goes through the Setup Assistant:
- Android Migration
- Display Tone
- Privacy
- iCloudStorage

### Assign Autopilot profiles to the All devices virtual group <!--2715522  -->
You'll be able to assign Autopilot profiles to the All devices virtual group. To do so, choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > choose a profile > **Assignments** > under **Assign to** choose **All devices**. For more information about Autopilot profiles, see [Enroll Windows devices by using Windows Autopilot](enrollment-autopilot.md).

### Customize wallpaper on supervised iOS devices using a device configuration profile <!-- 2809324  -->
When you create a device configuration profile for iOS devices, you will be able to allow and restrict some settings in **Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type. This update includes new **Wallpaper** settings that allow an Administrator to use a .png, .jpg, or .jpeg image as wallpaper, preview the image, and block users from changing the wallpaper. The wallpaper settings apply only to supervised devices. For a list of the current settings, see [iOS device restriction settings](device-restrictions-ios.md).

### Toast notifications for Win32 apps <!-- 3136566   -->
You will be able to suppress showing end user toast notifications per app assignment. From Intune, select **Client apps** > **Apps** > select the app > **Assignemnts** > **Include Groups**. 

### Contact Sharing via Bluetooth is removed in Device Restrictions > Device Owner for Android Enterprise <!-- 3598396 -->
When you create a device restrictions profile for Android Enterprise devices, there is a **Contact Sharing via Bluetooth** setting. In this update, the **Contact Sharing via Bluetooth** setting will be removed (**Device configuration** > **Profiles** > **Create profile** > **Android Enterprise** for platform > **Device Restrictions > Device owner** for profile type > **General**). 

The **Contact Sharing via Bluetooth** setting isn't supported for Android Enterprise Device Owner management. So when this setting is removed, it won't impact any devices or tenants, even if this setting is enabled and configured in your environment.

To see the current list of settings, go to [Android Enterprise device settings to allow or restrict features](device-restrictions-android-for-work.md).

Applies to: Android Enterprise Device Owner

<!-- 1812 start -->

### Android Enterprise APP-WE app deployment <!-- 1171203 -->
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you'll be able to use managed Google Play to deploy store apps and LOB apps to users. Specifically, IT can provide end users with an app catalog and installation experience that no longer requires end users to loosen the security posture of their devices by allowing installations from unknown sources. In addition, this deployment scenario will provide an improved end user experience.

### The Intune App SDK will support 256-bit encryption keys <!-- 1832174 -->
The Intune App SDK for Android will use 256-bit encryption keys when encryption is enabled by App Protection Policies. The SDK will continue to provide support of 128-bit keys for compatibility with content and apps that use older SDK versions.


### Intune policies update authentication method and Company Portal app installation  <!-- 1927359 -->
On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, Intune will no longer support the Company Portal when it is manually installed by end users from the app store. This change is only relevant when you authenticate with Apple Setup Assistant during enrollment. This change also only affects iOS devices enrolled through:  
* Apple configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

If users install the Company Portal app from the App store, and then try to enroll these devices through it, they will receive an error. These devices will be expected to only use Company Portal when it's been pushed, automatically, by Intune during enrollment. Enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. If you want your DEP device users to have the Company Portal, you will need to specify your preferences in an enrollment profile. 
In addition, the **Identify your device** screen in the Company Portal app will soon become obsolete.  
To install Company Portal on already-enrolled DEP devices, you will need to go to Intune > Client apps, and push it as a managed app with app configuration policies. Details about how to do these steps will be outlined in future docs.

### Non-Administrators can enable BitLocker on Windows 10 devices joined to Azure AD<!-- 2147379 -->
When you enable BitLocker settings on Windows 10 devices (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Endpoint protection** for profile type > **Windows Encryption**), you add BitLocker settings. 
This update includes a new BitLocker setting to allow standard users (non-administrators) to enable encryption. 
To see the current settings, see [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption).


### Additional settings for Outlook <!-- 3301182 -->
You can now configure additional settings for Outlook for iOS and Android using Intune.  The settings include the following:
- Only allow work or school accounts to be used in Outlook in iOS and Android
- Deploy modern authentication for Office 365 and hybrid modern authentication on-premises accounts
- Use `SAMAccountName` for the username field in the email profile when basic authentication is selected
- Allow contacts to be saved
- Configure External Recipients MailTips
- Configure **Focused Inbox**
- Require biometrics to access Outlook for iOS 
- Block external images

> [!NOTE]
> If you are using Intune App Protection policies to manage access for corporate identities, you should consider not enabling **require biometrics**. For more information, see **Require corporate credentials for access** for [iOS Access requirements](app-protection-policy-settings-ios.md#access-settings) and [Android Access requirements](app-protection-policy-settings-android.md#access-settings).

### Administrative templates are in public preview, and moved to their own configuration profile <!-- 3322847 -->
Administrative templates in Intune (**Device configuration** > **Administrative templates**) are currently in private preview. With this update:
Administrative templates includes about 300 settings that can be managed in Intune. Previously, these settings only existed in the group policy editor.
Administrative templates are available in public preview
Administrative templates are moving from **Device configuration** > **Administrative templates** to **Device configuration** > **Profiles** >**Create profile** > In **Platform**, choose **Windows 10 and later**, In **Profile type**, choose **Administrative templates**.
Reporting is enabled
Applies to: Windows 10 and later

### Intune macOS Company Portal Dark Mode <!-- 3300524 -->
The Intune macOS Company Portal now supports Dark Mode for macOS. When you enable Dark Mode on a macOS 10.14+ device, the Company Portal will adjust its appearance to colors the reflect that mode.

<!-- 1810 start -->

### Use Microsoft-recommended settings with Security Baselines <!-- 2055484 -->
Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator will be able to create security policies directly from these baselines, and then deploy them to their users. They can also customize the best practice recommendations to meet the needs of their organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

### Deployed WIP policies without user enrollment <!-- 1434452 -->
Windows Information Protection (WIP) policies will be able to be deployed without requiring MDM users to enroll their Windows 10 device. This configuration allows companies to protect their corporate documents based on the WIP configuration, while allowing the user to maintain management of their own Windows devices. Once documents are protected with a WIP policy, the protected data can be selectively wiped by an Intune administrator. By selecting the user and device, and sending a wipe request, all data that was protected via the WIP policy will become unusable. From the Intune in the Azure portal, select **Mobile app** > **App selective wipe**.


<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.



<!-- 1807 start -->

### Check for Configuration Manager compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). Configuration Manager sends signals to Intune compliance. Using the Intune setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later



## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



