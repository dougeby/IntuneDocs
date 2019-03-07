---
# required metadata

title: In development - Microsoft Intune
titlesuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata


#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection: M365-identity-device-management
---

# In development for Microsoft Intune - March 2019

To assist in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition:

- If we anticipate that you’ll need to take action prior to a change, we’ll publish a complimentary Office Message Center post.
- When a feature is launched in production, either as a preview or generally available, the feature description will move off this page and onto the [What's New page](whats-new.md).
- This page and the [What's New page](whats-new.md) are updated periodically. Check back for additional updates.
- Refer to the [M365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) for strategic deliverables and timelines.

> [!Note]
> These items reflect Microsoft’s current expectations about Intune capabilities coming in a future release. Dates and individual features may change. Not all items in development have a feature description on this page.


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal


<!-- 1903 start-->

### Encryption report  <!-- 2351538 -->
You'll be able to use a new Encryption report to view details about the encryption status of your devices. Available details will include a devices TPM version, encryption readiness and status, error reporting, and more.  

### Access BitLocker recovery keys from the Intune portal  <!-- 2351547  -->
We’re adding a new entry point in Devices, where you can view details from Azure Active Directory (AAD) about BitLocker Key ID and BitLocker recovery keys.

### Scope tags for app configuration policies <!--2371891 -->
You'll be able to add a scope tag to an app configuration policy so that only people with roles also assigned that scope tag have access to the app configuration policy. The app configuration policy can only be targeted to or associated with apps assigned the same scope tag.

### Assign Autopilot profiles to the All devices virtual group <!--2715522 -->
You'll be able to assign Autopilot profiles to the All devices virtual group. To do so, choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > choose a profile > **Assignments** > under **Assign to** choose **All devices**. For more information about Autopilot profiles, see [Enroll Windows devices by using Windows Autopilot](enrollment-autopilot.md).

### Install available apps using the Company Portal app after Windows bulk enrollment <!-- 2751523  -->
Windows devices that enrolled into Intune using [Windows bulk enrollment](windows-bulk-enroll.md) (provisioning packages) will be able to use the Company Portal app to install available apps. For more information about the Company Portal app, see [Manually add the Windows 10 Company Portal](store-apps-company-portal-app.md) and [How to configure the Microsoft Intune Company Portal app](company-portal-app.md).

### Scope tags for iOS app provisioning profiles <!--2934430 -->
You'll be able to add a scope tag to an iOS app provisioning profile so that only people with roles also assigned that scope tag have access to the iOS app provisioning profile. 

### Office Deployment Tool (ODT) XML for Office ProPlus deployment <!-- 3192477  -->
You'll be able to provide Office Deployment Tool (ODT) XML when creating an instance of Office Pro Plus in the Intune admin console. This will allow greater customizability if the existing Intune UI options do not meet your needs. 

###  Block users from scanning for Windows updates    <!-- 3316758    -->
We're adding a new Windows update ring setting that you can use that will block users from scanning for Windows updates. This setting won't be available from within the portal, but can be configured by using the Intune Graph API.

### Windows Update notifications  <!-- 3316782 -->
We're adding support to the Windows Update ring configurations so you'll be able to configure the Windows Update notifications that your users see. This setting won't be available from within the portal, but can be configured by using the Intune Graph API.

### Changes to Company Portal enrollment for iOS 12 device users <!--3448635 -->  
Company Portal for iOS will be updating the app's enrollment screens and steps to align with the MDM enrollment changes released in Apple iOS 12.2. The updated workflow will now prompt users to:

- Allow Safari to open the Company Portal website (via Safari) and download the management profile before returning to the Company Portal app. ​
- Open the Settings app to install the management profile on their device.​
- Return to the Company Portal app to complete enrollment.  ​

For more information about how you can prepare for these changes, see the [Microsoft Tech Community post](https://techcommunity.microsoft.com/]. In the meantime, to support new iOS enrollments in Company Portal, we've updated the steps in [Enroll iOS device in Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). These docs changes will be live after Apple releases iOS version 12.2. 

### Support for additional connectors on the Tenant Status page <!-- 3617202     -->
The Tenant Status page will display status information for additional connectors, including *Windows Defender Advanced Threat Protection* (ATP) and other Mobile Threat Defense connectors.

### Granting Intune read only access to some Azure Active Directory roles <!-- 3637917 -->
We'll be granting Intune read only access to the following Azure AD roles. Permissions granted with Azure AD roles supersede permissions granted with Intune role-based access control (RBAC).

Read only access to Intune audit data:

- Compliance Administrator
- Compliance Data Administrator

Read only access to all Intune data:

- Security Administrator
- Security Operator
- Security Reader
- Global Reader

### Easier access to Diagnostic Settings   <!-- 3804627   -->
We’re adding a new option to the **Audit logs** blade in every in every Audit Log workload in the Intune console that you can use to directly open the *Diagnostic Settings* page.

### Create and use device configuration profiles on Android Zebra devices in Intune <!-- 3895244  -->
Intune will support configuring Android Zebra devices. Specifically, you'll be able to: 

- Create a device configuration profile, and apply settings to Android Enterprise Zebra devices using OEMConfig (**Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform).
- Create a device configuration profile, and apply settings to Android Zebra devices using Mobility Extensions (MX) profiles generated by StageNow (**Device configuration** > **Profiles** > **Create profile** > **Android** for platform).

Applies to:  
- Android
- Android enterprise

<!-- 1901 start -->

### Deployment of online licensed Microsoft Store for Business apps <!-- 1672660  -->
You will be able to assign required online licensed Microsoft Store for Business apps in the device context. Deploying a Microsoft Store for Business app this way will enable the app to be installed for all users on the device. This is only applicable on Windows 10 RS4+ desktop devices. The option to install in the device context is available in the Client Apps assignment page for MSFB Online Licensed apps.

## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
