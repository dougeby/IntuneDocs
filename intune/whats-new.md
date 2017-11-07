---
# required metadata
title: What's new in Microsoft Intune
titlesuffix: "Azure portal"
description: Find out what's new in the Intune Azure portal
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 11/7/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# What's new in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Learn what’s new each week in Microsoft Intune. You can also find out about [upcoming changes](#whats-coming), [important notices](#notices) about the service, and information about [past releases](whats-new-archive.md).

> [!Note]
> Many of these features will eventually be supported for hybrid deployments with Configuration Manager. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   
## Week of November 6, 2017

<!-- ### App management -->

### Access to managed app logs for iOS <!-- 1469920 -->

End users with the managed Browser installed can now view the management status of all Microsoft published apps and send logs for troubleshooting their managed iOS apps.

Learn how to enable the troubleshooting mode in the Managed Browser on an iOS device, see [How to access to managed app logs using the Managed Browser on iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

<!-- Note for 1710 'What's New.... -->

## Week of October 30, 2017

### iOS and Android line-of-business app version number is visible <!-- 1380712 -->

Apps in Intune now display the version number for iOS and Android line-of-business apps. The number displays in the Azure portal in the app list and in the app overview blade. End users can see the app number in the Company Portal app and in the web portal.

#### Full version number

The full version number identifies a specific release of the app. The number appears as _Version_(_Build_). For example, 2.2(2.2.17560800)

The full version number has two components:

 - **Version**  
   The version number is the human-readable release number of the app. This is used by end users to identify different releases of the app.

 - **Build Number**  
    The build number is an internal number that can be used in app detection and to programmatically manage the app. The build number refers to an iteration of the app that references changes in the code.

Learn more about version numbers and developing line-of-business apps in [Get started with the Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

### Device and app management integration <!-- 677972 -->   
Now that Intune’s mobile device management (MDM) and mobile application management (MAM) are both accessible from the Azure portal, Intune started integrating the IT admin experience around application and device management. These changes are geared to simplify your device and app management experience.

Learn more about the MDM and MAM changes announced in the [Intune support team blog](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### New enrollment alerts for Apple devices <!-- 1471790 -->
The overview page for enrollment will show useful alerts for IT admins regarding management of Apple devices. Alerts will show up on Overview page when the Apple MDM push certificate is expiring or has already expired; when the Device Enrollment Program token is expiring or has already expired; and when there are unassigned devices in the Device Enrollment Program.


### Support token replacement for app configuration without device enrollment <!-- 1080364 -->

You can use tokens for dynamic values in app configurations for apps on devices that are not enrolled. For more information, see [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).

## Week of October 23, 2017

### Intune apps

#### Certificate-based authentication support on the Company Portal for iOS <!--1029830-->
We have added support for certificate-based authentication (CBA) in the Company Portal app for iOS. Users with CBA enter their username, then tap the “Sign in with a certificate” link. CBA is already supported on the Company Portal apps for Android and Windows. You can learn more on the [sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) page.

## Week of October 16, 2017

### Device enrollment
#### Windows AutoPilot Deployment Program support in Microsoft Intune  <!-- 747617  -->
You can now use Microsoft Intune with Windows AutoPilot Deployment Program to empower your users to provision their corporate devices without involving IT. You can customize the out-of-box experience (OOBE) and guide users to join their device to Azure AD and enroll in Intune. Working together, Microsoft Intune and Windows AutoPilot eliminate the need to deploy, maintain, and manage operating system images. For details, see [Enroll Windows devices using Windows AutoPilot Deployment Program](https://docs.microsoft.com/intune/enrollment-autopilot).

#### Quick start for device enrollment  <!-- 1425655 --> 
Quick start is now available in **Device enrollment** and provides a table of references for managing platforms and configuring the enrollment process. A brief description of each item and links to documentation with step-by-step instructions provides useful documentation to simplify getting started.

#### Device categorization <!-- 1427491 -->
The enrolled devices platform chart of the **Devices > Overview** blade organizes devices by platform, including Android, iOS, macOS, Windows, and Windows Mobile.  Devices running other operating systems are grouped into "Other."  This includes devices manufactured by Blackberry, NOKIA, and others.  

To learn which devices are affected in your tenant, choose **Manage > All devices** and then use **Filter** to limit the **OS** field.

### Device management
#### Zimperium - New Mobile Threat Defense partner   <!-- 954681 -->  
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense solution that integrates with Microsoft Intune.

##### How integration with Intune works
Risk is assessed based on telemetry collected from devices running Zimperium. You can configure EMS conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

#### New settings for Windows 10 device restriction profile  <!--- 978575, 1308849, -->  
We are adding new settings to the Windows 10 device restriction profile in the Windows Defender SmartScreen category.

For details about the Windows 10 device restriction profile, see [Windows 10 and later device restriction settings]( device-restrictions-windows-10.md).

#### Remote support for Windows and Windows Mobile devices   <!-- 1070473 -->  
Intune can now use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Windows, and Windows Mobile devices.

#### Scan devices with Windows Defender <!-- 1280988  1280990   -->
You can now run a **Quick scan**, **Full scan**, and **Update signatures** with Windows Defender Antivirus on managed Windows 10 devices. From the device's overview blade, choose the action to run on the device. You are prompted to confirm the action before the command is sent to the device. 

**Quick scan**: A quick scan scans locations where malware registers to start, such as registry keys and known Windows startup folders. A quick scan takes an average of five minutes. Combined with the **Always-on real-time protection** setting that scans files when they are opened, closed, and whenever a user navigates to a folder, a quick scan helps provide protection from malware that might be in the system or the kernel. Users see the scan results on their devices when it finishes. 

**Full scan**: A full scan can be useful on devices that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up, and is useful for running on-demand scans. Full scan can take an hour to run. Users see the scan results on their devices when it finishes. 

**Update signatures**: The update signature command updates Windows Defender Antivirus malware definitions and signatures. This helps ensure Windows Defender Antivirus is effective in detecting malware. This feature is for Windows 10 devices only, pending device internet connectivity. 

#### The Enable/Disable button is removed from the Intune Certificate Authority page of the Intune Azure portal  <!-- 1400455 -->
 We are eliminating an extra step in setting up the certificate connector on Intune. Currently, you download the certificate connector and then enable it in the Intune console. However, if you disable the connector in the Intune console, the connector continues to issue certificates.

##### How does this affect me?
Starting in October, the Enable/Disable button will no longer appear on the Certificate Authority page in the Azure portal. Connector functionality remains the same. Certificates are still deployed to devices enrolled in Intune. You can continue to download and install the certificate connector. To stop certificates from being issued, you now uninstall the certificate connector rather than disable it.

##### What do I need to do to prepare for this change?
If you currently have the certificate connector disabled, you should uninstall it.



### Device configuration
#### New settings for Windows 10 Team device restriction profile   <!--- 1308838 -->
In this release, we’ve added many new settings to the Windows 10 Team device restriction profile to help you control Surface Hub devices.

For more information about this profile, see [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md).

#### Prevent users of Android devices from changing their device date and time  <!-- 1333292 -->
You can use an [Android custom device policy](custom-settings-android.md) to prevent Android device users from changing the device date and time.

To do this, configure an Android custom policy with the setting URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange
Set this to **TRUE**, and then assign it to the required groups.

#### BitLocker device configuration <!-- 1397398 -->
The **Windows Encryption > Base Settings** include a new **Warning for another disk encryption** setting that lets you disable the [warning prompt](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) for other disk encryption that might be in use on the user's device.  The warning prompt requires end-user consent before setting up BitLocker on the device and blocks BitLocker setup until confirmed by the end-user.  The new setting disables the end-user warning.


### App management
#### Volume Purchase Program for Business apps will now sync to your Intune Tenant <!-- 800882 -->  
Third-party developers can privately distribute apps to authorized Volume Purchase Program (VPP) for Business members specified in iTunes Connect. These VPP for Business members can sign in to the Volume Purchase Program App Store and purchase their apps.

With this release, the VPP for Business apps purchased by the end user will now start syncing to their Intune tenants.

#### Select Apple country store to sync VPP apps  <!-- 1332311 -->  
You can configure the Volume Purchase Program (VPP) country store when uploading your VPP token. Intune synchronizes VPP apps for all locales from the specified VPP country store.

> [!NOTE]  
> Today, Intune only synchronizes VPP apps from the VPP country store that match the Intune locale in which the Intune tenant was created.




### Intune apps
#### Block copy and paste between work and personal profiles in Android for Work <!-- 1098994 -->
With this release, you are able to configure the work profile for  Android for Work to block copy and paste between work and personal apps. You can find this new setting in the **Device restrictions** profile for the **Android for Work** Platform in **Work profile settings**.

#### Create iOS apps limited to specific regional Apple App Stores <!-- 1281692 -->
You will be able to specify the country locale during the creation of an Apple App Store managed app.

> [!Note]  
> Currently, you can only create Apple App Store managed apps that are present in the US country store.

####  Update iOS VPP user and device licensed apps  <!-- 1305564 -->  
You will be able to configure the iOS VPP token to update all apps purchased for that token through the Intune service. Intune
will detect the VPP app updates inside the app store and automatically push them to the device when the device checks-in.

For steps to set an VPP token and enable automatic updates, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune]
(/intune/vpp-apps-ios).



### Monitor and troubleshoot
#### User device association entity Collection added to Intune Data Warehouse data model <!-- 1187917 -->
You can now build reports and data visualizations using the user device association information that associates user and device entity collections. The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client.

#### Review policy compliance for Windows 10 update rings <!-- 1067886 -->
You will be able to review a policy report for your Windows 10 update rings from Software updates > Per update ring deployment state. The policy report includes deployment status for the update rings that you have configured. 

#### New report that lists iOS devices with older iOS versions   <!-- 1352223 -->
The **Out-of-date iOS Devices** report is available from the **Software updates** workspace. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and have available updates. For each device, you can view a status for why the device has not been automatically updated. 

#### View app protection policy assignments for troubleshooting <!--  1475003 -->
In this upcoming release, **App protection policy** option will be added to the **Assignments** drop-down list available on the troubleshooting blade. You can now select app protection policies to see app protection policies assigned to the selected users.



## Week of October 2, 2017

### Intune apps
#### Improvements to device setup workflow in Company Portal <!--1490692-->
We've improved the device setup workflow in the Company Portal app for Android. The language is more user-friendly and specific to your company, and we've combined screens where possible. You can see these on the [what's new in app UI](whats-new-app-ui.md#week-of-october-2-2017) page.

#### Improved guidance around the request for access to contacts on Android devices <!--1484985-->

The Company Portal app for Android often requires the end user to accept the Contacts permission. If an end user declines this access, they will now see an in-app notification that alerts them to grant it for conditional access. 

#### Secure startup remediation for Android <!--1490712-->

End users with Android devices will be able to tap the non-compliance reason in the Company Portal app. When possible, this will take them directly to the correct location in the settings app to fix the issue. 

#### Additional push notifications for end users on the Company Portal app for Android Oreo <!--1475932-->

End users will see additional notifications to indicate to them when the Company Portal app for Android Oreo is performing background tasks, such as retrieving policies from the Intune service. This increases transparency for end users about when the Company Portal is performing administrative tasks on their device. This is part of the overall [optimization of the Company Portal UI](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) for the Company Portal app for Android Oreo. 

There are further optimizations for new UI elements that are enabled in Android Oreo.  End users will see additional notifications that will indicate to them when Company Portal is performing background tasks such as retrieving policy from the Intune service.  This increases transparency for end users about when Company Portal is performing administrative tasks on the device.

#### New behaviors for the Company Portal app for Android with work profiles <!---1485783--->

When you enroll an Android for Work device with a work profile, it's the Company Portal app in the work profile that performs management tasks on the device. 

Unless you are using a MAM-enabled app in the personal profile, the Company Portal app for Android no longer serves any use. To improve the work profile experience, Intune will automatically hide the personal Company Portal app after a successful work profile enrollment.

The Company Portal app for Android can be enabled at any time in the personal profile by browsing for [Company Portal in the Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and tapping **Enable**.

#### Company Portal for Windows 8.1 and Windows Phone 8.1 moving to sustaining mode <!--1428681-->

Beginning in October 2017, the Company Portal apps for Windows 8.1 and Windows Phone 8.1 will move to sustaining mode. This means that the apps and existing scenarios, such as enrollment and compliance, will continue to be supported for these platforms. These apps will continue to be available for download through existing release channels, such as the Microsoft Store. 

Once in sustaining mode, these apps will only will receive critical security updates. There will be no additional updates or features released for these apps. For new features, we recommend that you update devices to Windows 10 or Windows 10 Mobile. 


### Device enrollment

#### Block unsupported Samsung Knox device enrollment  <!--- 1490695 --->

The Company Portal app only attempts to enroll supported Samsung Knox devices. To avoid KNOX activation errors that prevent MDM enrollment, device enrollment is only attempted if the device appears in the [list of devices published by Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Samsung devices can have model numbers that support KNOX while others that don't. Verify Knox compatibility with your device reseller before purchase and deployment. You can find the full list of verified devices in the [Android and Samsung KNOX Standard policy settings](/intune/supported-devices-browsers.md#intune-supported-devices).

#### End of support for Android 4.3 and lower <!---1171126, 1326920 --->
Managed apps and the Company Portal app for Android will require Android 4.4 and higher to access company resources. By December, all enrolled devices will be force retired in December, resulting in loss of access to company resources. If you are using app protection policies without MDM, apps will not receive updates, and the quality of their experience will diminish over time.

#### Inform end users what device information can be seen on enrolled devices <!--1165314-->
We are adding **Ownership Type** to the Device Details screen on all Company Portal apps. This will allow users to find out more about privacy directly from the [What information can your company see?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) article. This will be rolling out across all Company Portal apps in the near future. We announced this for iOS in [September](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## Week of September 25, 2017

### Device enrollment

#### Intune supports iOS 11 <!--1428975-->
Intune supports iOS 11. This was previously announced on the [Intune Support blog](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### End of support for iOS 8.0 <!---1164477--->
Managed apps and the Company Portal app for iOS will require iOS 9.0 and higher to access company resources. Devices that aren't updated before this September will no longer be able to access the Company Portal or those apps. 

### Intune apps

#### Refresh action added to the Company Portal app for Windows 10 <!--1132468-->
The Company Portal app for Windows 10 allows users to refresh the data in the app by either pulling to refresh or, on desktops, pressing F5.



## Notices

### Deprecating support for OS X Mavericks 10.10 and previous versions of macOS <!--1489263, plan for change for 1802-->

We are announcing that we will begin deprecation of enrollment for devices with OS X Mavericks 10.10 and previous versions of macOS in February 2018. Intune fully supports OS X Yosemite 10.11 and newer.

### New path for managed devices in Graph API <!-- 1586728 -->
We are making a change to the path used to access managed devices in the beta version of the Graph API. 

| | |
|--|--|
| Current path |  https://graph.microsoft.com/beta/managedDevices |
| New path | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Both paths will work through the month of October. After the October service release, only the new path will work.  If you are using the Graph API to access managed devices, update and verify your scripts and applications with the new path. For additional changes, check the monthly [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog).


### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the Intune classic portal. Intune accounts created before January 2017 require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the Azure portal.

### Administration roles being replaced in Azure portal
The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to reassign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).



## What's coming

### Changes in support for the Intune iOS Company Portal app  <!-- 1164474  -->
Coming soon, there will be a new version of the Microsoft Intune Company Portal app for iOS that will support only devices running iOS 9.0 or later. The version of the Company Portal that supports iOS 8 will still be available for a very short period of time. However, note that if you also use MAM-enabled iOS apps we support iOS 9.0 and later, so you'll want to ensure your end users update to the latest OS. 

#### How does this affect me?
We are letting you know this in advance, even though we don't have specific dates, so you have time to plan. Ensure your users are updated to iOS 9+ and when the Company Portal app releases, request that your end users update their Company Portal app.

#### What do I need to do to prepare for this change?
Encourage your users to update to iOS 9.0 or later to take full advantage of new Intune features.  Encourage users to install the new
version of the Company Portal and take advantage of the new features it will offer.

Go to the Intune in the Azure portal and view Devices > All Devices and filter by iOS version to see any current devices with operating systems earlier than iOS 9.


### Apple to require updates for Application Transport Security <!--748318-->
Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps.

We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements. If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

## See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)
* [What's new in previous months](whats-new-archive.md)
