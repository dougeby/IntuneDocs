---
# required metadata

title: Early edition
description:
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
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

# The early edition for Microsoft Intune - July 2017

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on an extremely limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## What's coming to Intune on the Azure portal

### New app configuration settings for the Intune Managed Browser <!--- 682951 --->
We will add further configurations for the Intune Managed Browser app. You will be able to use an app configuration policy to configure the default home page and bookmarks for the browser.

### Restrict Android and iOS device enrollment restriction by OS version  <!--- 1333256,  1245463 --->  
Intune now supports restricting iOS and Android enrollment by operating system version number. Under **Device Type Restriction**, the IT admin can now set a platform configuration to restrict enrollment between a minimum and maximum operating system value. Android operating system versions must be specified as Major.Minor.Build.Rev, where Minor, Build and Rev are optional. iOS versions must be specified as Major.Minor.Build where Minor and Build are optional.

>[!NOTE]
>Does not restrict enrollment through Apple enrollment programs or Apple Configurator.

### Android for Work support for Lookout <!-- 1087312 -->   
Intune connector with Lookout will support Android for Work devices when using the Lookout for Work app. You will be able to deploy the Lookout app inside or outside the container.


### System Center Operations Manager management pack for Exchange connector <!-- 885457 -->   
The System Center Operations Manager management pack for Exchange connector will be available to help you parse the Exchange connector logs. This will give you different ways of monitoring Intune when you need to troubleshoot issues.

### New device action to force devices to sync with Intune <!-- 711369 -->    
We are adding a new device action that forces the selected device to immediately check-in with Intune. When a device checks-in, it immediately receives any pending actions or policies that have been assigned to it.  This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.

### Force supervised iOS devices to automatically install the latest available software update <!-- 777100 -->   
A new policy will be available from the Software updates workspace where you can force supervised iOS devices to automatically install the latest available software update. You will also be able to view a new report that lists iOS devices with older versions and a summary for why they are out of date.  

### New settings to allow and block apps on Samsung KNOX Standard devices  <!-- 822899,  1305423-->   
We are adding new [device restriction settings](device-restrictions-android.md) that let you specify the following app lists:
  - Apps that users are allowed to install
  - Apps that users are blocked from running
  - Apps that are hidden from the user on the device  

You can specify the app by URL, package name or from the list of apps you manage.

### Restrict Android, iOS, and macOS device personally owned device enrollment  <!--- 1333272,  1333275, 1245709 --->
Since January, Intune has offered to restrict personal device enrollment by white-listing corporate device IMEI numbers. Intune is expanding this functionality to iOS, Android, and macOS using device serial numbers. By uploading the serial numbers to Intune, you can predeclare devices as corporate-owned. Using enrollment restrictions, you can block personally owned (BYOD) devices, allowing enrollment only for corporate-owned devices.

To import serial numbers, go **Device enrollment** > **Corporate device identifiers** and click **Add** and then upload a .CSV file (no header, two columns for serial number and details like IMEI numbers).  To restrict personally owned devices, go **Device enrollment** > **Enrollment restrictions**. Under **Device Type Restrictions**, select the **Default** and then select **Platform Configurations**. You can **Allow** or **Block** personally owned devices for iOS, Android, and macOS. 



### Checkpoint - New Mobile Threat Defense partner  <!-- 1172027 -->
You will be able to control mobile device access to corporate resources using conditional access based on risk assessment conducted by Checkpoint, a mobile threat defense solution that integrates with Microsoft Intune.

#### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Checkpoint. You can configure EMS conditional access policies based on Checkpoint risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

### Check Point SandBlast Mobile - New Mobile Threat Defense partner  <!-- 954651 -->  
You will be able to control mobile device access to corporate resources using conditional access based on risk assessment conducted by Checkpoint SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.

#### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Checkpoint SandBlast Mobile. You can configure EMS conditional access policies based on Checkpoint SandBlast Mobile risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

### Zimperium - New Mobile Threat Defense partner   <!-- 954681 -->
You will be able to control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense solution that integrates with Microsoft Intune.

#### How integration with Intune works?
Risk is assessed based on telemetry collected from devices running Zimperium. You can configure EMS conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.


### On-premises Exchange connector high availability support  <!-- 676614 -->   
You will be able to have multiple Client Access Server (CAS) roles for on-premises Exchange connector. For example, if the main CAS fails, the Exchange connector receives a query to fall back to other CASs. This feature ensures that the service is not interrupted.

### Conditional access support for Mac devices  <!-- 720172 -->   
You will soon be able to set a conditional access policy that requires Mac devices to be enrolled into Intune and compliant with its device compliance policies. For example, users can download the Intune Company Portal app for macOS and enroll their Mac devices into Intune. Intune evaluate whether the Mac device is compliant or not with requirements like PIN, encryption, OS version, and System Integrity.





### Actions for non-compliance  <!--730266-->     
*Actions for non-compliance* is a new feature of compliance policies that will let you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### End of support for iOS 8.0 <!---1164477--->
Managed apps and the Company Portal app for iOS will require iOS 9.0 and higher to access company resources. Devices that aren't updated before this September will no longer be able to access the Company Portal or those apps. By December, all access to company resources, including email, will be prevented. 

### Android Support Updates  <!-- ? -->
Beginning in October, Microsoft Intune and the Intune Company Portal app will move to support Android 4.4 and higher. Users on unsupported versions of Android will not be able to access or enroll using the Company Portal app. Enrolled devices that are on the affected Android versions will continue to remain enrolled until December. If devices are still enrolled in December, they will be force-retired from Intune resulting in loss of access to company resources. If using Application Protection Policies without enrollment, applications will not receive updates, and the quality of the experience may diminish over time. To block access to company resources on applications on older operating systems, see our Conditional Access offerings.



### Platform Support Reminder: Windows Phone 8.1 mainstream support will end July 11, 2017 <!-- 1327781 -->  
On July 11, 2017,  the Windows Phone 8.1 platform will reach end of mainstream support. Windows 8.1 PC support is not impacted.

There is no immediate impact to any Windows Phone 8.1 device that is managed by the Intune service. Devices that are enrolled will continue to work and all policies, configurations, and apps will continue to work as expected. Please note, there are no improvements targeted for the Windows Phone 8.1 platform within the Intune Service, and for the Windows Phone 8.1 Company Portal app.

We recommend upgrading eligible Windows Phone 8.1 devices to Windows 10 Mobile at your earliest opportunity. 




## What's coming to Intune apps

### Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123-->    
We are announcing a change that is coming in the next few months that will improve the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows. The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change. In addition, users can now sign in to the Company Portal from another device with a generated, single-use code. This is especially useful in cases when users need to sign in without credentials.

You can find screenshots of the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device on the [What's new in app UI](whats-new-app-ui.md) page.

### Enable end users to tag their device group in the Company Portal app for Windows 10 <!---807046-->    
End users will be able to select which group their device belongs to by tagging it directly from within the Company Portal app for Windows 10.

### Users who are signed in to Exchange can automatically access the Company Portal website on Windows 10 devices <!--1323204-->  
Windows 10 users that are already authenticated in Exchange, who receive the conditional access quarantine email and click the link in the email, will no longer need to re-authenticate in the browser before beginning Company Access Setup.


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
