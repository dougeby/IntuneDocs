---
# required metadata
title: What's new in previous months in the Microsoft Intune
titlesuffix: "Azure portal"
description: Review older announcements from the Intune what's new page
keywords:
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# What's new in the Microsoft Intune - previous months

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## September 2017

### Inform end users what device information can be seen for iOS <!--739894-->

We have added  **Ownership Type** to the Device Details screen on the Company Portal app for iOS. This will allow users to find out more about privacy directly from this page from the Intune end user docs. They will also be able to locate this information on the About screen.

### Allow end users to access the Company Portal app for Android without enrollment <!---1169910--->

End users will soon not have to enroll their device to access the Company Portal app for Android. End users at organizations that are using App Protection Policies will no longer receive prompts to enroll their device when they open the Company Portal app. End users will also be able to install apps from the Company Portal without enrolling the device. 


### Easier-to-understand phrasing for the Company Portal app for Android <!---1396349--->  

The enrollment process for the Company Portal app for Android has been simplified with new text to make it easier for end users to enroll. If you have custom enrollment documentation, you will want to update it to reflect the new screens. You can find sample images on our [UI updates for Intune end user apps](whats-new-app-ui.md#week-of-september-11-2017) page.

### Windows 10 Company Portal app added to Windows Information Protection allow policy <!-- 677129 -->

The Windows 10 Company Portal app has been updated to support Windows Information Protection (WIP). The app can be added to the WIP allow policy. With this change, the app no longer has to be added to the **Exempt** list.


## August 2017

### Improvements to device overview <!-- 1404453 -->  
Improvements to the device overview now display enrolled devices but excludes devices managed by Exchange ActiveSync. Exchange ActiveSync devices do not have the same management options as enrolled devices. To view the number of enrolled devices and number of enrolled devices by platform in Intune in the Azure portal, go **Devices** > **Overview**.

### Improvements to device inventory collected by Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
In this release, we’ve made the following improvements to the inventory information collected by devices you manage:
 
-   For Android devices, you can now add a column to device inventory that shows the latest patch level for each device. Add the **Security patch level** column to your device list to see this.
-   When you filter the device view, you can now filter devices by their enrollment date. For example, you could display only devices that were enrolled after a date you specify.
-   We’ve made improvements to the filter used by the **Last Check-in Date** item.
-   In the device list, you can now display the phone number of corporate owned devices.
Additionally, you can use the filter pane to search for devices by phone number.
 
For more details about device inventory, see [How to view Intune device inventory](device-inventory.md).

### Conditional access support for macOS devices 
<!-- 720172 -->
You can now set a conditional access policy that requires Mac devices to be enrolled into Intune and compliant with its device compliance policies. For example, users can download the Intune Company Portal app for macOS and enroll their Mac devices into Intune. Intune evaluate whether the Mac device is compliant or not with requirements like PIN, encryption, OS version, and System Integrity.

- Learn more about [conditional access support for macOS devices](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### Company Portal app for macOS is in public preview <!---1484796--->
The Company Portal app for macOS is now available as part of the public preview for conditional access in Enterprise Mobility + Security. This release supports macOS 10.11 and above. Get it at [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### New device restriction settings for Windows 10    
<!--1063965, 1308850  -->
In this release, we’ve added new settings for the [Windows 10 device restriction profile](/intune/device-restrictions-windows-10) in the following categories:

-   Windows Defender SmartScreen
-   App store

### Updates to the Windows 10 endpoint protection device profile for BitLocker settings
<!--1459533 -->    
In this release, we’ve made the following improvements to how BitLocker settings work in a Windows 10 endpoint protection device profile:
 
Under **Bitlocker OS drive settings**, for the setting **BitLocker with non-compatible TPM chip**, when you select **Block**, previously, this would cause BitLocker to actually be allowed. We have now fixed this to block BitLocker when it is selected.
Under **Bitlocker OS drive settings**, for the setting **Certificate-based data recovery agent**, you can now explicitly block the certificate-based data recovery agent. By default, however, the agent is allowed.
Under **BitLocker fixed data-drive settings**, for the setting **Data recovery agent**, you can now explicitly block the data recovery agent.
For more information, see [Endpoint protection settings for Windows 10 and later](endpoint-protection-windows-10.md).


### New signed-in experience for Android Company Portal users and App Protection Policy users <!-- 621669 -->
End users can now browse apps, manage devices, and view IT contact information using the Android Company Portal app without enrolling their Android devices. In addition, if an end user already uses an app protected by Intune App Protection Policies and launches the Android Company Portal, the end user no longer receive a prompt to enroll the device.

### New setting in the Android Company Portal app to toggle battery optimization <!--1405990-->
The **Settings** page in the Company Portal app for Android has a new setting that easily lets users turn off battery optimization for Company Portal and Microsoft Authenticator apps. The app name shown in the setting will vary depending on which app manages the work account. We recommend that users turn battery optimization off for better performance of work apps that sync email and data. 

### Multi-identity support for OneNote for iOS      <!-- 1234281 -->
End users can now use different accounts (work and personal) with Microsoft OneNote for iOS. App protection policies can be applied to corporate data in work notebooks without affecting their personal notebooks. For example, a policy can allow a user to find information in work notebooks, but will prevent the user from copying and pasting and corporate data from the work notebook to a personal notebook.
 
- Learn more about the apps that support [app protection and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.

### New settings to allow and block apps on Samsung Knox Standard devices
<!-- 1305423 822899-->  
In this release, we are adding new [device restriction settings](device-restrictions-android.md) that let you specify the following app lists:
 
- Apps that users are allowed to install
- Apps that users are blocked from running
- Apps that are hidden from the user on the device
 
You can specify the app by URL, package name or from the list of apps you manage.

### New Azure AD app-based conditional access policy UI link from Intune
<!-- 1016201 -->
IT admins can now set app-based conditional policies via the new conditional access policy UI in the Azure AD workload. The app-based conditional access that is in the Intune App Protection section in the Azure portal will remain there for the time being and will be enforced side-by-side. There’s also a convenience link to the new conditional access policy UI in the Intune workload.

- Learn more about [app-based conditional access on Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## July 2017

### Restrict Android and iOS device enrollment restriction by OS version  <!--- 1333256,  1245463 --->
Intune now supports restricting iOS and Android enrollment by operating system version number. Under **Device Type Restriction**, the IT admin can now set a platform configuration to restrict enrollment between a minimum and maximum operating system value. Android operating system versions must be specified as Major.Minor.Build.Rev, where Minor, Build and Rev are optional. iOS versions must be specified as Major.Minor.Build where Minor and Build are optional. Learn more about [device enrollment restrictions](enrollment-restrictions-set.md).

>[!NOTE]
>Does not restrict enrollment through Apple enrollment programs or Apple Configurator.

### Restrict Android, iOS, and macOS device personally owned device enrollment  <!--- 1333272,  1333275, 1245709 --->
Intune can restrict personal device enrollment by white-listing corporate device IMEI numbers. Intune has now expanded this functionality to iOS, Android, and macOS using device serial numbers. By uploading the serial numbers to Intune, you can predeclare devices as corporate-owned. Using enrollment restrictions, you can block personally owned (BYOD) devices, allowing enrollment only for corporate-owned devices. Learn more about [device enrollment restrictions](enrollment-restrictions-set.md).

To import serial numbers, go **Device enrollment** > **Corporate device identifiers** and click **Add** and then upload a .CSV file (no header, two columns for serial number and details like IMEI numbers).  To restrict personally owned devices, go **Device enrollment** > **Enrollment restrictions**. Under **Device Type Restrictions**, select the **Default** and then select **Platform Configurations**. You can **Allow** or **Block** personally owned devices for iOS, Android, and macOS. 


### New device action to force devices to sync with Intune <!-- 711369 -->
In this release, we've added a new device action that forces the selected device to immediately check-in with Intune. When a device checks in, it immediately receives any pending actions or policies that have been assigned to it.  This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.
For details, see [Synchronize device](device-sync.md)

### Force supervised iOS devices to automatically install the latest available software update <!-- 777100 -->
A new policy is available from the Software updates workspace where you can force supervised iOS devices to automatically install the latest available software update. For details see, [Configure iOS update policies](/intune/software-updates-ios)

### Check Point SandBlast Mobile - New Mobile Threat Defense partner  <!-- 954651, 1172027 -->
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Checkpoint SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.

#### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Checkpoint SandBlast Mobile. You can configure EMS conditional access policies based on Checkpoint SandBlast Mobile risk assessment enabled through Intune device compliance policies. You can allow or block non-compliant devices access to corporate resources based on detected threats.


### Deploy an app as available in the Microsoft Store for Business <!-- 748101 -->
With this release, admins can now assign the Microsoft Store for Business as available. When set as available, end-users can install the app from the Company Portal app or website without being redirected to the Microsoft Store.

### UI updates to the Company Portal website <!--1313244 part 1-->
We made several updates to the UI of the [Company Portal website](https://portal.manage.microsoft.com) to enhance the end user experience.

- __Enhancements to app tiles__:  App icons will now display with an automatically generated background based on the dominant color of the icon (if it can be detected). When applicable, this background replaces the gray border that was previously visible on app tiles.

    The Company Portal website displays large icons whenever possible in an upcoming release. We recommend that IT admins publish apps using high-resolution icons with a minimum size of 120 x120 pixels. 

- __Navigation changes__: Navigation bar items are moved to the hamburger menu in the top left. The Categories page is removed. Users can now filter content by category while browsing.

- __Updates to Featured Apps__: We've added a dedicated page to the site where users can browse apps that you've chosen to feature, and made some UI tweaks to the Featured section on the homepage.

### iBooks support for the Company Portal website <!--1231841-->
We've added a dedicated page to the Company Portal website that allows users to browse and download iBooks. 


### Additional help desk troubleshooting details <!---  Applies to 1263399, 1326964, 1341642 --->
Intune has updated the troubleshooting display and added to the information that it provides for admins and help desk staff. You can now see an **Assignments** table that summarizes all assignments for the user based on group membership. This list includes:
- Mobile apps
- Compliance policies
- Configuration profiles
 
In addition, the **Devices** table now includes **Azure AD join type** and **Azure AD compliant** columns. For more information, see [help users troubleshoot problems](help-desk-operators.md).



### Intune Data Warehouse (Public Preview)
The Intune Data Warehouse samples data daily to provide a historical view of your tenant. You can access the data using a Power BI file (PBIX), an OData link that is compatible with many analytics tools, or interacting with the REST API. For more information, see [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).


### Light and dark modes available for the Company Portal app for Windows 10 <!---676547--->
End users will be able to customize the color mode for the Company Portal app for Windows 10. The user is able to make the change in the Settings section of the Company Portal app. The change will appear after the user has restarted the app. For Windows 10 version 1607 and later, the app mode will default to the system setting. For Windows 10 version 1511 and earlier, the app mode will default to the light mode.

### Enable end users to tag their device group in the Company Portal app for Windows 10 <!---807046-->
End users are now able to select which group their device belongs to by tagging it directly from within the Company Portal app for Windows 10.



## June 2017

### New role-based administration access for Intune admins   <!-- 1099990 -->  
A new conditional access admin role is being added to view, create, modify, and delete Azure AD Conditional Access policies. Previously, only global admins and security admins had this permission. Intune admins can be granted with this role permission so that they have access to conditional access policies.


### Tag corporate-owned devices with serial number <!-- 1215070 -->  
Intune now supports uploading iOS, macOS, and Android serial numbers as Corporate Device Identifiers. You can't use serial numbers to block personal devices from enrolling at this time because serial numbers are not verified during enrollment. Blocking personal devices by serial number will be released in the near future.


### New remote actions for iOS devices <!-- 854689 -->
In this release, we've added two new remote device actions for shared iPad devices that manage the Apple Classroom app:

- 	[Logout current user](device-logout-user.md) - Logs out the current user of an iOS device you choose.
- 	[Remove user](device-remove-user.md) - Deletes a user you choose from the local cache on an iOS device.


### Support for shared iPads with the iOS Classroom app <!-- 1044681 -->
In this release, we've expanded the support for managing the iOS Classroom app to include students who log into shared iPads using their managed Apple ID.


### Changes to Intune built-in apps <!-- 1332306 -->
Previously, Intune contained a number of built-in apps that you could quickly assign. Based on your feedback, we have removed this list, and you will no longer see built-in apps.
However, if you have already assigned any built-in apps, these will still be visible in the list of apps. You can continue to assign these apps as required.
In a later release, we plan to add an easier method to select and assign built-in apps from the Azure portal.

### Easier installation of Office 365 apps <!--- 1121362 --->
The new **Office 365 ProPlus** app type makes it easy for you to assign Office 365 ProPlus 2016 apps to devices that you manage which run the latest version of Windows 10. Additionally, you can also install Microsoft Project, and Microsoft Visio, if you own licenses for them. The apps you want are bundled together and appear as one app in the list of apps in the Intune console.
For more information, see [How to add Office 365 apps for Windows 10](apps-add-office365.md).


### Support for offline apps from the Microsoft Store for Business <!--- 777044 --->
Offline apps you purchased from the Microsoft Store for Business will now be synchronized to the Azure portal. You can then deploy these apps to device groups, or user groups. Offline apps are installed by Intune, and not by the store.

### Microsoft teams is now part of the App-based CA list of approved apps   <!-- 1257019 -->
The Microsoft Teams app for iOS and Android is now part of approved apps for app-based conditional access policies for Exchange and SharePoint Online. The app can be configured through the Intune App Protection blade in the Azure portal to all tenants currently using app-based conditional access.

### Managed browser and app proxy integration <!-- 1287310 -->
The Intune Managed Browser can now integrate with the Azure AD Application Proxy service to let users access internal web sites even when they are working remotely. Users of the browser simply enter the site URL as they normally would and the Managed Browser routes the request through the application proxy web gateway. For more information, see [Manage Internet access using Managed browser policies](app-configuration-managed-browser.md).

### New app configuration settings for the Intune Managed Browser <!-- 682951 -->
In this release, we've added further configurations for the Intune Managed Browser app for iOS and Android. You can now use an app configuration policy to configure the default home page and bookmarks for the browser.
For more information, see [Manage Internet access using Managed browser policies](app-configuration-managed-browser.md)

### BitLocker settings for Windows 10  <!-- 951707 -->
You can now configure BitLocker settings for Windows 10 devices using a new Intune device profile. For example, you can require that devices are encrypted, and also configure further settings that are applied when BitLocker is turned on.
For more information, see [Endpoint protection settings for Windows 10 and later](endpoint-protection-windows-10.md).

### New settings for Windows 10 device restriction profile <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
In this release, we've added new settings for the Windows 10 device restriction profile, in the following categories:

-  Windows Defender
-  Cellular and connectivity
-  Locked screen experience
-  Privacy
-  Search
-  Windows Spotlight
-  Edge browser

For more information about Windows 10 settings, see [Windows 10 and later device restriction settings](device-restrictions-windows-10.md).


### Company Portal app for Android now has a new end user experience for App Protection Policies <!--1305217-->
Based on customer feedback, we've modified the Company Portal app for Android to show an **Access Company Content** button. The intent is to prevent end users from unnecessarily going through the enrollment process when they only need to access apps that support App Protection Policies, a feature of Intune mobile application management. You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.

### New menu action to easily remove Company Portal <!--1164569-->
Based on user feedback, the Company Portal app for Android has added a new menu action to initiate the removal of Company Portal from your device. This action removes the device from Intune management so that the app can be removed from the device by the user. You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page and in the [Android end user documentation](/intune-user-help/unenroll-your-device-from-intune-android).

### Improvements to app syncing with Windows 10 Creators Update <!--676505-->
The Company Portal app for Windows 10 will now automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (version 1703). This will reduce the issue of app installs stalling during the "Pending Sync" state. In addition, users will be able to manually initiate a sync from within the app. You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.

### New guided experience for Windows 10 Company Portal <!---1058938--->
The Company Portal app for Windows 10 will include a guided Intune walkthrough experience for devices that have not been identified or enrolled. The new experience provides step-by-step instructions that guide the user through registering into Azure Active Directory (required for Conditional Access features) and MDM enrollment (required for device management features). The guided experience will be accessible from the Company Portal home page. Users can continue to use the app if they do not complete registration and enrollment, but will experience limited functionality.

This update is only visible on devices running Windows 10 Anniversary Update (build 1607) or higher. You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.


### Microsoft Intune and Conditional Access admin consoles are generally available
We’re announcing the general availability of both the new Intune in the Azure portal admin console and the Conditional Access admin console. Through Intune in the Azure portal, you can now manage all Intune MAM and MDM capabilities in one consolidated admin experience, and leverage Azure AD grouping and targeting. Conditional access in Azure brings rich capabilities across Azure AD and Intune together in one unified console. And from an administrative experience, moving to the Azure platform allows you to use modern browsers.

Intune is now visible without the **preview** label in the Azure portal at portal.azure.com.

There is no action required for existing customers at this time, unless you have received one of a series of messages in the message center requesting that you take action so that we can migrate your groups. You may have also received a message center notice informing you that migration is taking longer due to bugs on our side. We are diligently continuing work to migrate any impacted customer.

### Improvements to the app tiles in the Company Portal app for iOS
We updated the design of the app tiles on the homepage to reflect the branding color you set for the Company Portal. For more information, see [what's new in app UI](whats-new-app-ui.md).

### Account picker now available for the Company Portal app for iOS
Users of iOS devices might see our new account picker when they sign into the Company Portal if they use their work or school account to sign into other Microsoft apps. For more information, see [what's new in app UI](whats-new-app-ui.md).

## May 2017

### Change your MDM authority without unenrolling managed devices <!--1103950-->
You can now change your MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. In the Configuration Manager console, you can [change your MDM authority](/sccm/mdm/deploy-use/change-mdm-authority) from Set to Configuration Manager (hybrid) to Microsoft Intune (standalone) or vice versa.


### Improved notification for Samsung Knox startup PINs <!--1087143-->
When end users need to set a start-up PIN on Samsung Knox devices to become compliant with encryption, the notification displayed to end users will bring them to the exact place in the Settings app when the notification is tapped.  Previously, the notification brought the end user to the password change screen.

### Device enrollment

#### Apple School Manager (ASM) support with shared iPad <!-- 748864, 770395-->

Intune now supports use of Apple School Manager (ASM) in place of Apple Device Enrollment Program to provide out-of-box enrollment of iOS devices. ASM onboarding is required to use the Classroom app for Shared iPads, and is required to enable syncing data from ASM to Azure Active Directory via Microsoft School Data Sync (SDS). For more information, see [Enable iOS device enrollment with Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Configuring Shared iPads to work with the Classroom app requires iOS Education configurations in Azure are that not yet available.  This functionality will be added soon.

### Device management

#### Provide remote assistance to Android devices using TeamViewer <!-- 675418 -->

Intune can now use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices. For more information, see [Provide remote assistance for Intune managed Android devices](device-profile-android-teamviewer.md).

### App management

#### New app protection policies conditions for MAM <!-- 679864 -->

You can now set a requirement for MAM without enrollment users that enforces the following policies:

- Minimum application version
- Minimum operating system version
- Minimum Intune APP SDK version of the targeted application (iOS only)

This feature is available on both Android and iOS. Intune supports minimum version enforcement for OS platform versions, application versions, and Intune APP SDK. On iOS, applications that have the SDK integrated can also set a minimum version enforcement at the SDK level. The user will be unable to access the targeted application if the minimum requirements through the app protection policy are not met at the three different levels mentioned above. At this point, the user may either remove their account (for multi-identity applications), close the application, or update the version of the OS or application.

You can also configure additional settings to provide a non-blocking notification that recommends an OS or application upgrade. This notification can be closed and the application may be used as normal.

For more information, see [iOS app protection policy settings](app-protection-policy-settings-ios.md) and [Android app protection policy settings](app-protection-policy-settings-android.md).

#### Configure app configurations for Android for Work <!-- 621621 -->
Some Android apps from the store support managed configuration options that let an IT admin control how an app runs in the work profile. With Intune, you can now view the configurations supported by an app, and configure them from the Azure portal with a configuration designer or a JSON editor. For more information, see [Use app configurations for Android for Work](app-configuration-policies-use-android.md).

#### New app configuration capability for MAM without enrollment <!-- 677969 -->
You can now create app configuration policies through the MAM without enrollment channel. This feature is equivalent to the app configuration policies available in the mobile device management (MDM) app configuration. For an example of app configuration using MAM without enrollment, see  [Manage Internet access using Managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).

#### Configure allowed and blocked URL lists for the Managed Browser <!-- 682960 -->
You can now configure a list of allowed and blocked domains and URLs for the Intune Managed Browser using app configuration settings in the Azure portal. These settings can be configured regardless of whether it is being used on a managed or unmanaged device. For more information, see [Manage Internet access using Managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).

#### App protection policy helpdesk view <!-- 1069473 -->
IT Helpdesk users can now check user license status and the status of app protection policy apps assigned to users in the Troubleshooting blade. For details, see [Troubleshooting](./help-desk-operators.md).

### Device configuration

#### Control website visits on iOS devices <!-- 723832 -->
You can now control which websites users of iOS devices can visit using one of the following two methods:

- Add permitted, and blocked URLs using Apples built-in web content filter.

- Allow only specified websites to be accessed by the Safari browser. Bookmarks are created in Safari for each site you specify.

For more information, see [Web content filter settings for iOS devices](web-content-filter-settings-ios.md).

#### Preconfigure device permissions for Android for Work apps <!-- 621614 -->
For apps deployed to Android for Work device work profiles, you can now configure the permissions state for individual apps.  By default, Android apps that require device permissions such as access to location or the device camera will prompt users to accept or deny permissions.  For example, if an app uses the device's microphone, then the end user is prompted to grant the app permission to use the microphone. This feature allows you to define permissions on behalf of the end user.  You can configure permissions to a) automatically deny without notifying the user, b) automatically approve without notifying the user, or c) prompt the user to accept or deny. For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).

#### Define app-specific PIN for Android for Work devices <!-- 728976, 1102534 -->
Android 7.0 and above devices with a work profile managed as an Android for Work device let the administrator define a passcode policy that only applies to apps in the work profile.  Options include:

- Define just a device-wide passcode policy - This is the passcode that the user must use to unlock their entire device.
- Define just a work profile passcode policy - Users will be prompted to enter a passcode whenever any app in the work profile is opened.
- Define both a device and work profile policy - IT admin has the choice to define both a device passcode policy and a work profile passcode policy at differing strengths (for example, a four-digit PIN to unlock the device, but a six-digit PIN to open any work app).

For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> This is only available on Android 7.0 and above.  By default, the end user can use the two separately defined PINs or they can elect to combine the two defined PINs into the strongest of the two.

#### New settings for Windows 10 devices <!-- 978585 -->
We've added new [Windows device restriction settings](device-restrictions-windows-10.md) that control features like wireless displays, device discovery, task switching, and SIM card error messages.

#### Updates to certificate configuration <!-- 918991 and 823198 -->
When creating a SCEP certificate profile, for **Subject name format**, the **Custom** option is available for iOS, Android, and Windows devices. Before this update, the **Custom** field was available for iOS devices only. For more information, see [ How to create a SCEP certificate profile] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

When creating a PKCS certificate profile, for **Subject alternative name**, the **Custom Azure AD attribute** is available. The **Department** option is available when you select **Custom Azure AD attribute**. For more information, see [How to create a PKCS certificate profile](certficates-pfx-configure.md#create-a-device-configuration-profile).

#### Configure multiple apps that can run when an Android device is in kiosk mode <!-- 662059 -->
When an Android device is in kiosk mode, you could previously only configure one app that was allowed to run. You can now configure multiple apps using the app ID, store URL, or by selecting an Android app you already manage. For more information, see [Kiosk mode settings](device-restrictions-android.md#kiosk).



## April 2017

### Support for managing the Apple Classroom app
You can now manage the iOS Classroom app on iPad devices. Set up the Classroom app on the teachers iPad with the correct class and student data, then configure student iPads registered to a class, so that you can control them using the app.
For details, see [Configure iOS education settings](education-settings-configure-ios.md).

### Support for managed configuration options for Android apps <!-- 621621 -->
Android apps in the Play store that support managed configuration options can now be configure by Intune.  This feature lets IT view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.

### New Android policy for complex PINs <!-- 722069 -->
You can now set a required [password](device-restrictions-android.md#password) type of Numeric complex in an Android device profile for devices that run Android 5.0 and above.  Use this setting to prevent device users from creating a PIN that contains repeating, or consecutive numbers, like 1111, or 1234.

### Additional support for Android for Work devices
- **Manage password and work profile settings** <!-- 612808 -->

  This new Android for Work device restriction policy now lets you manage password and work profile settings on Android for Work devices you manage.

- **Allow data sharing between work and personal profiles** <!-- 1045102 -->

This Android for Work device restriction profile now has new options to help you configure data sharing between work and personal profiles.

- **Restrict copy and paste between work and personal profiles** <!-- 1046094 -->

  A new custom device profile for Android for Work devices now lets you restrict whether copy and paste actions between work and personal apps are allowed.

For more information, see [Device restrictions for Android for Work](device-restrictions-android-for-work.md).

### Assign LOB apps to iOS and Android devices <!-- 1057568 -->
You can now assign line of business (LOB) apps for [iOS](lob-apps-ios.md) (.ipa files) and [Android](lob-apps-android.md) (.apk files) to users or devices.


###  New device policies for iOS <!-- 723774, 723815, 723826, 723830 -->
- **Apps on Home screen** - Controls which apps users see on the [Home screen of their iOS device](home-screen-settings-ios.md). This policy changes the layout of the Home screen, but does not deploy any apps.

- **Connections to AirPrint devices** - Controls which [AirPrint devices](air-print-settings-ios-macos.md) (network printers) that end users of iOS device can connect to.

- **Connections to AirPlay devices** - Controls which [AirPlay devices](airplay-settings-ios.md) (like Apple TV) that end users of iOS device can connect to.

- **Custom lock screen message** - Configures a custom message that users will see on the lock screen of their iOS device, that replaces the default lock screen message. For more information, see [Activate lost mode on iOS devices](device-lost-mode.md)

### Restrict push notifications for iOS apps <!-- 723767 -->
In an Intune device restriction profile, you can now configure the following [notification settings](app-notification-settings-ios.md) for iOS devices:

- Fully turn on or off notification for a specified app.
- Turn on or off, the notification in the notification center for a specified app.
- Specify the alert type, either **None**, **Banner**, or **Modal Alert**.
- Specify whether badges are allowed for this app.
- Specify whether notification sounds are allowed.

### Configure iOS apps to run in single app mode autonomously <!-- 737837 -->
You can now use an Intune device profile to configure iOS devices to run specified apps in [autonomous single app mode](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). When this mode is configured, and the app is run, the device is locked so that it can only run that app. An example of this is when you configure an app that lets users take a test on the device. When the app's actions are complete, or you remove this policy, the device returns to its normal state.

### Configure trusted domains for email and web browsing on iOS devices <!-- 723765 -->
From an iOS device restriction profile, you can now configure the following [domain settings](device-restrictions-ios.md#domains):

- **Unmarked email domains** - Emails that the user sends or receives which don't match the domains you specify here will be marked as untrusted.

- **Managed web domains** - Documents downloaded from the URLs you specify here will be considered managed (Safari only).  

- **Safari password auto-fill domains** - Users can save passwords in Safari only from URLs matching the patterns you specify here. To use this setting, the device must be in supervised mode and not configured for multiple users. (iOS 9.3+)


### VPP apps available in iOS Company Portal <!-- 748782 -->
You can now assign iOS volume-purchased (VPP) apps as **Available** installs to end users. End users will need an Apple Store account to install the app.

### Synchronize eBooks from Apple VPP Store <!-- 800878 -->
You can now [synchronize books](vpp-apps-ios.md) you purchased from the Apple volume-purchase program store with Intune, and assign the books to users.

### Multi-user management for Samsung Knox Standard devices <!-- 971988 -->
Devices that run Samsung Knox Standard are now supported for [multi-user management](android-enroll.md) by Intune. This means that end users can sign in and out of the device with their Azure Active Directory credentials, and the device is centrally managed whether it’s in use or not.  When end-users sign-in, they have access to apps and get any policies applied to them. When users sign out, all app data is cleared.

### Additional Windows device restriction settings <!-- 818566 -->
We've added support for additional [Windows device restriction settings](device-restrictions-windows-10.md) like additional Edge browser support, device lock screen customization, start menu customizations, Windows Spotlight search set wallpaper, and proxy setting.

### Multi-user support for Windows 10 Creators Update <!-- 822547 -->
We've added support for [multi-user management](windows-enroll.md) for devices that run the Windows 10 Creators Update and are Azure Active Directory domain-joined. This means that when different standard users log into the device with their Azure AD credentials, they will receive any apps and policies that were assigned to their user name. Users cannot currently use the Company Portal for self-service scenarios like installing apps.

### Fresh Start for Windows 10 PCs<!-- 1004830 -->
A new [Fresh Start device action](device-fresh-start.md) for Windows 10 PCs is now available.  When you issue this action, any apps that were installed on the PC are removed, and the PC is automatically updated to the latest version of Windows. This can be used to help remove pre-installed OEM apps that are often delivered with a new PC. You can configure if user data is retained when this device action is issued.

### Additional Windows 10 upgrade paths <!-- 903672 -->
You can now create an [edition upgrade policy to upgrade devices](edition-upgrade-configure-windows-10.md) to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Bulk Enroll Windows 10 devices <!-- 747607 -->
You can now join large numbers of devices that run the Windows 10 Creators update to Azure Active Directory and Intune with Windows Configuration Designer (WCD). To enable [bulk MDM enrollment](windows-bulk-enroll.md) for your Azure AD tenant, create a provisioning package that joins devices to your Azure AD tenant using Windows Configuration Designer, and apply the package to corporate-owned devices you'd like to bulk enroll and manage. Once the package is applied to your devices, they will Azure AD join, enroll in Intune, and be ready for your Azure AD users to log on.  Azure AD users are standard users on these devices and receive assigned policies and required apps. Self-service and Company Portal scenarios are not supported currently.

### New MAM settings for PIN and managed storage locations <!-- 581122, 736644 -->
Two new app settings are now available to help you with mobile application management (MAM) scenarios:

- **Disable app PIN when device PIN is managed** - Detects if a device PIN is present on the enrolled device, and if so, bypasses the app PIN triggered by the app protection policies. This setting will allow for a reduction in the number of times a PIN prompt is displayed to users opening a MAM-enabled application on an enrolled device. This feature is available for both Android and iOS.

- **Select which storage services corporate data can be saved to** -Allows you to specify which storage locations in which to save corporate data. Users can save to the selected storage location services, which means all other storage location services not listed will be blocked.

  List of supported storage location services:

  - OneDrive
  - Business SharePoint Online
  - Local storage

### Help desk troubleshooting portal <!-- 907448 -->
The new [troubleshooting portal](help-desk-operators.md) lets help desk operators and Intune administrators view users and their devices, and perform tasks to resolve Intune technical problems.

## March 2017

### Support for iOS Lost Mode <!--431695-->
For iOS 9.3 and later devices, Intune added support for **Lost Mode**. You can now lock down a device to prevent all use and display a message and contact phone number of the device lock screen.

The end user will not be able to unlock the device until an admin disables Lost Mode. When Lost Mode is enabled, you can use the **Locate device** action to display the geographical location of the device on a map in the Intune console.

The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.

For more information, see [What is Microsoft Intune device management](device-management.md)?

### Improvements to Device Actions report <!--677150-->
We’ve made improvements to the Device Actions report to improve performance. Additionally, you can now filter the report by state. For example, you could filter the report to show only device actions that were completed.”

### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](apps-add.md).

### Assign LOB apps to users with unenrolled devices <!--748823-->
You can now assign line-of-business apps from the store to users whether or not their devices are enrolled with Intune. If the user's device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.

### New compliance reports <!--846671-->
You now have compliance reports that give you the compliance posture of devices in your company and allow you to quickly troubleshoot compliance-related issues encountered by your users. You can view information about

- Overall compliance state of devices
- Compliance state for an individual setting
- Compliance state for an individual policy

You can also use these reports to drill down into an individual device to view specific settings and policies that affect that device.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the Azure portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.


## February 2017

### Ability to restrict mobile device enrollment <!--747600, 795782-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.

* Restricting mobile device enrollment does not restrict PC client enrollment.  
* For iOS and Android only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### View all actions on managed devices <!--677150-->
A new __Device Actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action. See [What is device management?](device-management.md).

### Non-managed devices can access assigned apps <!--664691-->
As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](apps-add.md).

### Display device categories <!--814654-->
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade. See [How to add an app to Intune](apps-add.md).

### Configure Windows Update for Business settings <!--776716-->

Windows as a Service is the new way of providing updates for Windows 10. Starting with Windows 10, any new Feature Updates and Quality Updates will contain the contents of all previous updates. This means that as long as you've installed the latest update, you know that your Windows 10 devices are completely up-to-date. Unlike with previous versions of Windows, you now must install the entire update instead of part of an update.

By using Windows Update for Business, you can simplify the update management experience so that you don’t need to approve individual updates for groups of devices. You can still manage risk in your environments by configuring an update rollout strategy and Windows Update will make sure that updates are installed at right time. Microsoft Intune provides the ability to configure update settings on devices and gives you the ability to defer update installation. Intune doesn’t store the updates, but only the update policy assignment. Devices access Windows Update directly for the updates.Use Intune to configure and manage **Windows 10 update rings**. An update ring contains a group of settings that configure when and how Windows 10 updates get installed. For details, see [Configure Windows Update for Business settings](windows-update-for-business-configure.md).
