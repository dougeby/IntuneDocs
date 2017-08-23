---
# required metadata

title: Early edition
description:
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
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
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# The early edition for Microsoft Intune - August 2017

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## Intune on the Azure portal

### Actions for non-compliance  <!--730266-->     
*Actions for non-compliance* are a new feature of compliance policies that let you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### New report that lists iOS devices with older iOS versions   <!-- 1352223 -->
The **Out-of-date iOS Devices** report will be available from the **Software updates** workspace. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and have available updates. For each device, you can view a status for why the device has not been automatically updated. 

### New settings to allow and block apps on Samsung KNOX Standard devices  <!-- 822899,  1305423-->   
We are adding new [device restriction settings](device-restrictions-android.md) that let you specify the following app lists:
  - Apps that users are allowed to install
  - Apps that users are blocked from running
  - Apps that are hidden from the user on the device  

You can specify the app by URL, package name or from the list of apps you manage.

### New settings for Windows 10 device restriction profile
<!--- 978575, 1308849, 1308850 -->
We are adding new settings to the Windows 10 device restriction profile in the Windows Defender SmartScreen category.

For details about the Windows 10 device restriction profile, see [Windows 10 and later device restriction settings]( device-restrictions-windows-10.md).

### New device restriction settings for Windows 10   <!-- 1063965 -->
We are adding new settings for the [Windows 10 device restriction profile](/intune/device-restrictions-windows-10) in the following categories:
- Windows Defender SmartScreen
- App store


### Android for Work support for Lookout <!-- 1087312 -->   
Intune connector with Lookout will support Android for Work devices when using the Lookout for Work app. You are able to deploy the Lookout app inside or outside the container.


### Intune App Protection and Citrix MDX Development Tools <!-- 709185 -->
You can manage devices and apps with a combination of Citrix XenMobile MDX and Microsoft Intune. This allows you to manage apps with Intune app protection policy while using Citrix’s mVPN technology.

You are able to find a code repository that contains the Intune App Wrapping Tool and Intune App SDK for iOS and Android, integrating with Citrix MDX mVPN technology.


### Zimperium - New Mobile Threat Defense partner   <!-- 954681 -->
You are able to control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense solution that integrates with Microsoft Intune.

#### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Zimperium. You can configure EMS conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

### New Azure AD conditional access policy UI link from Intune  <!-- 1016201 -->
IT admins can set app-based conditional policies via the new conditional access policy UI in Azure AD workload. The app-based conditional access policies that are in the Intune App Protection section in Azure remain there for the time being and are enforced side-by-side. There will also be a convenience link to the new conditional access policy UI in Azure AD from the Intune workload.


### On-premises Exchange connector high availability support  <!-- 676614 -->   
You are able to have multiple Client Access Server (CAS) roles for on-premises Exchange connector. For example, if the main CAS fails, the Exchange connector receives a query to fall back to other CASs. This feature ensures that the service is not interrupted.

### System Center Operations Manager management pack for Exchange connector <!-- 885457 -->   
The System Center Operations Manager management pack for Exchange connector will be available to help you parse the Exchange connector logs. This management pack gives you different ways of monitoring Intune when you need to troubleshoot issues.

### End of support for iOS 8.0 <!---1164477--->
Managed apps and the Company Portal app for iOS will require iOS 9.0 and higher to access company resources. Devices that aren't updated before this September will no longer be able to access the Company Portal or those apps. By December, all access to company resources, including email, will be prevented. 

### End of support for Android 4.3 and lower <!---1171127, 1326920 --->
Managed apps and the Company Portal app for Android will require Android 4.4 and higher to access company resources. Devices that aren't updated before the beginning of October will no longer be able to access the Company Portal or those apps. By December, all enrolled devices will be force retired in December, resulting in loss of access to company resources. If you are using app protection policies without MDM, apps will not receive updates, and the quality of their experience will diminish over time.


### Platform Support Reminder: Windows Phone 8.1 mainstream support will end July 11, 2017 <!-- 1327781 -->  
On July 11, 2017,  the Windows Phone 8.1 platform will reach end of mainstream support. Windows 8.1 PC support is not impacted.

There is no immediate impact to any Windows Phone 8.1 device that is managed by the Intune service. Devices that are enrolled continue to work and all policies, configurations, and apps will continue to work as expected. Please note, there are no improvements targeted for the Windows Phone 8.1 platform within the Intune Service, and for the Windows Phone 8.1 Company Portal app.

We recommend upgrading eligible Windows Phone 8.1 devices to Windows 10 Mobile at your earliest opportunity. 

## Intune apps

### Intune Managed Browser support for iOS and Android <!---1374196--->

As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later. Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.

### Allow end users to access the Company Portal app for Android without enrollment <!---1169910--->  
End users will soon not have to enroll their device to access the Company Portal app for Android. End users at organizations that are using App Protection Policies will no longer receive prompts to enroll their device when they open the Company Portal app. End users will also be able to install apps from the Company Portal without enrolling the device. 

### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."

### New signed-in experience for Android Company Portal users and App Protection Policy users <!-- 621669 -->
End users will be able to browse apps, manage devices, and view IT contact information using the Android Company Portal app without enrolling their Android devices. In addition, if an end user already uses an app protected by Intune App Protection Policies and launches the Android Company Portal, the end user will no longer receive a prompt to enroll the device. 

### Inform end users what device information can be seen for iOS <!--739894-->
We are adding **Ownership Type** to the Device Details screen on the Company Portal app for iOS. This allows users to find out more about privacy directly from this page from the Intune end-user docs. They will also be able to locate this information on the About screen.

### Apps details pages display new information for Android devices <!--1287476-->
The apps detail page of the Company Portal app for Android will display the app categories that the IT admin has defined for that app.

### Intune Mobile Application Management (MAM) dialog boxes now have a modern interface <!-- 1199015 -->
Intune Mobile Application Management (MAM) dialog boxes have been updated to the modern look-and-feel. The dialog boxes function in the same way as the previous style.

On modern Android devices, error or notification dialog boxes displayed by Intune will now show updated look-and-feel.

### New setting in the Android Company Portal app to toggle battery optimization <!--1405990-->
The **Settings** page in the Company Portal app for Android will have a new setting that easily lets users turn off battery optimization for Company Portal and Microsoft Authenticator apps. The app name shown in the setting varies depending on which app manages the work account. We recommend that users turn off battery optimization for better performance of work apps that sync email and data. 




## Notices

### Apple to require updates for Application Transport Security <!--748318-->   
Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### Direct access to Apple enrollment scenarios <!--951869-->   
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.

### Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 -->
We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.  

If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.

Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage. Moving forward as a partner, please use one of these sites to manage your customers.



### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
