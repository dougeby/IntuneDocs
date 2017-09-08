---
# required metadata

title: Early edition
description:
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
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

# The early edition for Microsoft Intune - September 2017

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices

-->



## Intune in the Azure portal


### Google Play Protect support on Android <!-- 908720  -->  
With the release of Android Oreo, Google introduces a suite of security features called Google Play Protect that allow users and organizations to run secure apps and secure Android images. Intune will support Google Play Protect features, including SafetyNet remote attestation.  Admins can set compliance policy requirements that require Google Play Protect be configured and healthy. The **SafetyNet device attestation** setting requires the device to connect with a Google service to verify that the device is healthy and is not compromised. Admins can also set a configuration profile setting for Android for Work to require that installed apps are verified by Google Play services.  Conditional access might block users from accessing corporate resources if a device is not compliant with Google Play Protect requirements. 

### Prevent users of Android devices from changing their device date and time  <!-- 1333292 -->
You can use an [Android custom device policy](custom-settings-android.md) to prevent Android device users from changing the device date and time.
To do this, configure an Android custom policy with the setting URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange
Set this to **TRUE**, and then assign it to the required groups.

### View app protection policy assignments for troubleshooting <!--  1475003 -->
In this upcoming release, **App protection policy** option will be added to the **Assignments** drop-down list available on the troubleshooting blade. You can now select app protection policies to see app protection policies assigned to the selected users.

### Create iOS apps limited to specific regional Apple App Stores <!-- 1281692 -->
You will be able to specify the country locale during the creation of an Apple App Store managed app.

> [!NOTE]  
> Currently, you can only create Apple App Store managed apps that are present the US country store.

### Select Apple country store to sync VPP apps  <!-- 1332311 -->  
You can configure the Volume Purchase Program (VPP) country store when uploading your VPP token. Intune synchronizes VPP apps for all locales from the specified VPP country store.

> [!NOTE]  
> Today, Intune only synchronizes VPP apps from the VPP country store that match the Intune locale in which the Intune tenant was created.

###  Update iOS VPP user and device licensed apps  <!-- 1305564 -->  
You will be able to configure the iOS VPP token to update all apps purchased for that token through the Intune service. Intune will detect the VPP app updates inside the app store and automatically push them to the device when the device checks-in.

### iOS 11 support <!-- 1428975 -->
When released by Apple, Intune will support iOS 11.

### New settings for Windows 10 Team device restriction profile  <!--- 1308838  -->
In this release, we are adding many new settings to the Windows 10 Team device restriction profile to help you control Surface Hub devices.
For more information about this profile, see [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md).

### Support for Windows 10 edition upgrade policy   <!-- 903672, 1119689 -->  
You will be able to create a Windows 10 edition upgrade policy that upgrades Windows 10 devices to Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education and Windows 10 Professional Education N.
For details about Windows 10 edition upgrades, see [How to configure Windows 10 edition upgrades ](edition-upgrade-configure-windows-10.md).

### Review policy compliance for Windows 10 update rings <!-- 1352223 -->  
You will be able to review a policy report for your Windows 10 update rings from **Software updates** > **Per update ring deployment state**. The policy report includes deployment status for the update rings that you have configured. 

### Windows 10 Company Portal app added to Windows Information Protection allow policy <!-- 677129 -->  
The Windows 10 Company Portal app will be updated to support Windows Information Protection (WIP). The app can be added to the WIP allow policy. With this change, the app no longer has to be added to the **Exempt** list. 

### Remote support for Windows, and Windows Mobile devices  <!-- 1070473 -->    
Intune will be able to use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Windows, and Windows Mobile devices.

### Scan devices with Windows Defender <!-- 1280988  1280990   -->
You will be able to run a **Quick scan**, **Full scan**, and **Update signatures** with Windows Defender Antivirus on managed Windows 10 devices. From the device's overview blade, choose the action to run on the device. You are prompted to confirm the action before the command is sent to the device. 

**Quick scan**: A quick scan scans locations where malware registers to start, such as registry keys and known Windows startup folders. A quick scan takes an average of five minutes. Combined with the **Always-on real-time protection** setting that scans files when they are opened, closed, and whenever a user navigates to a folder, a quick scan helps provide protection from malware that might be in the system or the kernel. Users see the scan results on their devices when it finishes. 

**Full scan**: A full scan can be useful on devices that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up, and is useful for running on-demand scans. Full scan can take an hour to run. Users see the scan results on their devices when it finishes. 

**Update signatures**: The update signature command updates Windows Defender Antivirus malware definitions and signatures. This helps ensure Windows Defender Antivirus is effective in detecting malware. This feature is for Windows 10 devices only, pending device internet connectivity. 

### BitLocker device configuration <!-- 1397398 -->  
The **Windows Encryption > Base Settings** will include a new **Warning for another disk encryption** setting that lets you disable the [warning prompt](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) for other disk encryption that might be in use on the user's device.  The warning prompt requires end-user consent before setting up BitLocker on the device and blocks BitLocker setup until confirmed by the end-user.  The new setting disables the end-user warning.

### Company Portal for Windows 8.1 and Windows Phone 8.1 moving to sustaining mode <!--1428681-->
Beginning in October 2017, the Company Portal apps for Windows 8.1 and Windows Phone 8.1 will move to sustaining mode. This means that the apps and existing scenarios, such as enrollment and compliance, will continue to be supported for these platforms. These apps will continue to be available for download through existing release channels, such as the Microsoft Store. 

Once in sustaining mode, these apps will only will receive critical security updates. There will be no additional updates or features released for these apps. For new features, we recommend that you update devices to Windows 10 or Windows 10 Mobile. 

###  Block copy and paste between work and personal profiles in Android for Work <!-- 1098994 -->   
With this release, you are able to configure the work profile for  Android for Work to block copy and paste between work and personal apps. You can find this new setting in the **Device restrictions** profile for the **Android for Work** Platform in **Work profile settings**.

### New behaviors for the Company Portal app for Android with work profiles <!---1485783--->
When you enroll an Android for Work device with a work profile, it's the Company Portal app in the work profile that performs management tasks on the device. 
Unless you are using a MAM-enabled app in the personal profile, the Company Portal app for Android no longer serves any use. To improve the work profile experience, Intune will automatically hide the personal Company Portal app after a successful work profile enrollment.

The Company Portal app for Android can be enabled at any time in the personal profile by browsing for [Company Portal in the Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and tapping **Enable**.

### Intune MAM & Outlook for Android add-ins  <!-- 1450688 -->
In a few weeks, the Office team will announce add-ins for Outlook on Android. This add-in feature set already exists in Outlook on Windows, iOS, web and Mac. Because add-ins are managed via Exchange, users will be able to copy and share data and messages across Outlook and unmanaged add-in applications, unless access to add-ins is turned off by your Exchange admin. 

To manage user access permissions to add-ins, work with your Exchange admin to ensure that your MAM data protection policies apply to add-ins.

#### How does this affect me?
If your Exchange policies are already set to prevent side loading add-ins or installing add-ins, then read no further. Your MAM policies will apply as expected. If, however, you have set policies in MAM to restrict cut, copy, and paste operations within Outlook on Android and have not set your add-in policy in Exchange, you should know that by default, users will be able to install add-ins to Outlook. These add-ins can access message body, subject and other message properties. You can turn off end-user ability to install add-ins by having your Exchange Admin remove the “My Marketplace Apps” and “My Custom Apps” roles. For more details, see the additional information link shared below.

Note that the setting change in Exchange will apply to Outlook across Windows, iOS, web, Mac and mobile. 

#### What do I need to do?
Review your Exchange policies today. Inform your IT and helpdesk staff. Contact our support team with any specific questions or concerns. 

### User device association entity Collection added to Intune Data Warehouse data model <!-- 1187917 -->
You will be able to build reports and data visualizations using the user device association information that associates user and device entity collections. The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client.


<!-- the following are present prior to 1709 -->

### Actions for non-compliance  <!--730266-->     
*Actions for non-compliance* are a new feature of compliance policies that let you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### New report that lists iOS devices with older iOS versions   <!-- 1352223 -->
The **Out-of-date iOS Devices** report will be available from the **Software updates** workspace. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and have available updates. For each device, you can view a status for why the device has not been automatically updated. 

### New settings for Windows 10 device restriction profile
<!--- 978575, 1308849, -->
We are adding new settings to the Windows 10 device restriction profile in the Windows Defender SmartScreen category.

For details about the Windows 10 device restriction profile, see [Windows 10 and later device restriction settings]( device-restrictions-windows-10.md).

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
### Refresh action added to the Company Portal app for Windows 10 <!--1132468-->
The Company Portal app for Windows 10 will allow users to refresh the data in the app by either pulling to refresh or, on desktops, pressing F5.


### Apps that are available with or without enrollment can now be installed without being prompted for enrollment. <!-- 1334712 -->
Company apps that have been made available with or without enrollment on the Android Company Portal app can be installed without a prompt to enroll.

### iOS Company Portal display large icons <!-- 1454593 -->
We are fixing a known issue with how the iOS Company Portal displays icons in the app tile. If you upload app icons of 120x120 pixels or larger, they now display in the [Company Portal website] (https://portal.manage.microsoft.com) and the iOS Company Portal's apps pages at the full size of the app tile.

### Easier to understand phrasing for the Company Portal app for Android   <!---1396349--->    
The enrollment process for the Company Portal app for Android has been simplified with new text to make it easier for end users to enroll. 


<!-- the following are present prior to 1709 -->


### Intune Managed Browser support for iOS and Android <!---1374196--->
As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later. Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.

### Allow end users to access the Company Portal app for Android without enrollment <!---1169910--->  
End users will soon not have to enroll their device to access the Company Portal app for Android. End users at organizations that are using App Protection Policies will no longer receive prompts to enroll their device when they open the Company Portal app. End users will also be able to install apps from the Company Portal without enrolling the device. 

### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."

### Inform end users what device information can be seen for iOS <!--739894-->
We are adding **Ownership Type** to the Device Details screen on the Company Portal app for iOS. This allows users to find out more about privacy directly from this page from the Intune end-user docs. They will also be able to locate this information on the About screen.

### Apps details pages display new information for Android devices <!--1287476-->
The apps detail page of the Company Portal app for Android will display the app categories that the IT admin has defined for that app.

### Intune Mobile Application Management (MAM) dialog boxes now have a modern interface <!-- 1199015 -->
Intune Mobile Application Management (MAM) dialog boxes have been updated to the modern look-and-feel. The dialog boxes function in the same way as the previous style.

On modern Android devices, error or notification dialog boxes displayed by Intune will now show updated look-and-feel.



## Notices
### Apple to require updates for Application Transport Security <!--748318-->   
Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 -->
We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.  

If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.

Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage. Moving forward as a partner, please use one of these sites to manage your customers.



### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
