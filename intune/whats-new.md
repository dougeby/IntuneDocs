---
# required metadata
title: What's new in Microsoft Intune
titleSuffix: "Intune on Azure"
description: Find out what's new in the Intune Azure portal
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 08/14/2017
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
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   


## Week of August 21, 2017
### App management
#### New signed-in experience for Android Company Portal users and App Protection Policy users <!-- 621669 -->

End users can now browse apps, manage devices, and view IT contact information using the Android Company Portal app without enrolling their Android devices. In addition, if an end user already uses an app protected by Intune App Protection Policies and launches the Android Company Portal, the end user no longer receive a prompt to enroll the device.

## Week of July 31, 2017
### Device enrollment  

#### Restrict Android and iOS device enrollment restriction by OS version  <!--- 1333256,  1245463 --->
Intune now supports restricting iOS and Android enrollment by operating system version number. Under **Device Type Restriction**, the IT admin can now set a platform configuration to restrict enrollment between a minimum and maximum operating system value. Android operating system versions must be specified as Major.Minor.Build.Rev, where Minor, Build and Rev are optional. iOS versions must be specified as Major.Minor.Build where Minor and Build are optional. Learn more about [device enrollment restrictions](enrollment-restrictions-set.md).

>[!NOTE]
>Does not restrict enrollment through Apple enrollment programs or Apple Configurator.

#### Restrict Android, iOS, and macOS device personally owned device enrollment  <!--- 1333272,  1333275, 1245709 --->
Intune can restrict personal device enrollment by white-listing corporate device IMEI numbers. Intune has now expanded this functionality to iOS, Android, and macOS using device serial numbers. By uploading the serial numbers to Intune, you can predeclare devices as corporate-owned. Using enrollment restrictions, you can block personally owned (BYOD) devices, allowing enrollment only for corporate-owned devices. Learn more about [device enrollment restrictions](enrollment-restrictions-set.md).

To import serial numbers, go **Device enrollment** > **Corporate device identifiers** and click **Add** and then upload a .CSV file (no header, two columns for serial number and details like IMEI numbers).  To restrict personally owned devices, go **Device enrollment** > **Enrollment restrictions**. Under **Device Type Restrictions**, select the **Default** and then select **Platform Configurations**. You can **Allow** or **Block** personally owned devices for iOS, Android, and macOS. 


### Device management   

#### New device action to force devices to sync with Intune <!-- 711369 -->
In this release, we've added a new device action that forces the selected device to immediately check-in with Intune. When a device checks in, it immediately receives any pending actions or policies that have been assigned to it.  This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.
For details, see [Synchronize device](device-sync.md)

#### Force supervised iOS devices to automatically install the latest available software update <!-- 777100 -->
A new policy is available from the Software updates workspace where you can force supervised iOS devices to automatically install the latest available software update. For details see, [Configure iOS update policies](/intune/software-updates-ios)

#### Check Point SandBlast Mobile - New Mobile Threat Defense partner  <!-- 954651, 1172027 -->
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Checkpoint SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.

##### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Checkpoint SandBlast Mobile. You can configure EMS conditional access policies based on Checkpoint SandBlast Mobile risk assessment enabled through Intune device compliance policies. You can allow or block non-compliant devices access to corporate resources based on detected threats.


### App management

#### Deploy an app as available in the Microsoft Store for Business <!-- 748101 -->
With this release, admins can now assign the Microsoft Store for Business as available. When set as available, end-users can install the app from the Company Portal app or website without being redirected to the Microsoft Store.


### Intune apps  

#### UI updates to the Company Portal website <!--1313244 part 1-->
We made several updates to the UI of the [Company Portal website](https://portal.manage.microsoft.com) to enhance the end user experience.

- __Enhancements to app tiles__:  App icons will now display with an automatically generated background based on the dominant color of the icon (if it can be detected). When applicable, this background replaces the gray border that was previously visible on app tiles.

    The Company Portal website displays large icons whenever possible in an upcoming release. We recommend that IT admins publish apps using high-resolution icons with a minimum size of 120 x120 pixels. 

- __Navigation changes__: Navigation bar items are moved to the hamburger menu in the top left. The Categories page is removed. Users can now filter content by category while browsing.

- __Updates to Featured Apps__: We've added a dedicated page to the site where users can browse apps that you've chosen to feature, and made some UI tweaks to the Featured section on the homepage.

#### iBooks support for the Company Portal website <!--1231841-->
We've added a dedicated page to the Company Portal website that allows users to browse and download iBooks. 

### Monitor and troubleshoot

#### Additional help desk troubleshooting details <!---  Applies to 1263399, 1326964, 1341642 --->
 
Intune has updated the troubleshooting display and added to the information that it provides for admins and help desk staff. You can now see an **Assignments** table that summarizes all assignments for the user based on group membership. This list includes:
- Mobile apps
- Compliance policies
- Configuration profiles
 
In addition, the **Devices** table now includes **Azure AD join type** and **Azure AD compliant** columns. For more information, see [help users troubleshoot problems](help-desk-operators.md).

### Reporting

#### Intune Data Warehouse (Public Preview)

The Intune Data Warehouse samples data daily to provide a historical view of your tenant. You can access the data using a Power BI file (PBIX), an OData link that is compatible with many analytics tools, or interacting with the REST API. For more information, see [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).

## Week of July 23rd, 2017

### Light and dark modes available for the Company Portal app for Windows 10 <!---676547--->
End users will be able to customize the color mode for the Company Portal app for Windows 10. The user is able to make the change in the Settings section of the Company Portal app. The change will appear after the user has restarted the app. For Windows 10 version 1607 and later, the app mode will default to the system setting. For Windows 10 version 1511 and earlier, the app mode will default to the light mode.

### Enable end users to tag their device group in the Company Portal app for Windows 10 <!---807046-->
End users are now able to select which group their device belongs to by tagging it directly from within the Company Portal app for Windows 10.




## Notices

### IP addresses for Intune updated <!-- 1175274 -->
An [updated list of DNS names and IP addresses](/intune/network-bandwidth-use) is available for firewall proxy settings.

### Use Azure Active Directory for conditional access <!-- 967947 -->
Conditional access is available in the Azure Active Directory section of the Azure console and provides a more powerful and flexible framework for setting policies for cloud apps like Office 365 Exchange Online and SharePoint Online.  Use the **Conditional access in Azure Active Directory** blade to configure policies instead of the classic Intune console. Existing policies in the classic Intune console need to be re-created in the Azure console. For more information, see [Create Azure AD conditional access policies](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the Azure portal.

### Administration roles being replaced in Azure portal
The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to reassign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).



## What's coming

### End of support for iOS 8.0 <!---1164477--->
Managed apps and the Company Portal app for iOS will require iOS 9.0 and higher to access company resources. Devices that aren't updated before this September will no longer be able to access the Company Portal or those apps. 

### UI updates to the Company Portal website <!--1313244 part 2-->
__Updates to Featured Apps__  
We've added a dedicated page to the site where users can browse apps that you've chosen to feature, and made some UI tweaks to the Featured section on the homepage. You can see what these changes look like on the [what's new in app UI](whats-new-app-ui.md) page.


### End of support for Android 4.3 and lower <!---1171127, 1326920 --->
Managed apps and the Company Portal app for Android will require Android 4.4 and higher to access company resources. Devices that aren't updated before the beginning of October will no longer be able to access the Company Portal or those apps. By December, all enrolled devices will be force retired in December, resulting in loss of access to company resources. If you are using app protection policies without MDM, apps will not receive updates, and the quality of their experience will diminish over time.


### Platform Support Reminder: Windows Phone 8.1 mainstream support ended July 11, 2017
<!-- 1327781 -->
On July 11, 2017,  the Windows Phone 8.1 platform reached end of mainstream support. Windows 8.1 PC support is not impacted.

There is no immediate impact to any Windows Phone 8.1 device that is managed by the Intune service. Devices that are enrolled will continue to work and all policies, configurations, and apps will continue to work as expected. Note that there are no improvements targeted for the Windows Phone 8.1 platform within the Intune Service, and for the Windows Phone 8.1 Company Portal app.

We recommend that you upgrade eligible Windows Phone 8.1 devices to Windows 10 Mobile at your earliest opportunity. 

### Changes in support for the Intune iOS Company Portal app  <!-- 1164474  -->
Coming soon, there will be a new version of the Microsoft Intune Company Portal app for iOS that will support only devices running iOS 9.0 or later. The version of the Company Portal that supports iOS 8 will still be available for a very short period of time. However, note that if you also use MAM-enabled iOS apps we support iOS 9.0 and later, so you'll want to ensure your end users update to the latest OS. 

#### How does this affect me?
We are letting you know this in advance, even though we don't have specific dates, so you have time to plan. Ensure your users are updated to iOS 9+ and when the Company Portal app releases, request that your end users update their Company Portal app.

#### What do I need to do to prepare for this change?
Encourage your users to update to iOS 9.0 or later to take full advantage of new Intune features.  Encourage users to install the new
version of the Company Portal and take advantage of the new features it will offer.

Go to the Intune on Azure portal and view Devices > All Devices and filter by iOS version to see any current devices with operating systems earlier than iOS 9.


### Apple to require updates for Application Transport Security <!--748318-->
Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps.

We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements. If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)
* [What's new in previous months](whats-new-archive.md)
