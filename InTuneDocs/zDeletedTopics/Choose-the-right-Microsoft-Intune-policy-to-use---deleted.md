---
title: Choose the right Microsoft Intune policy to use - deleted
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 65ec39cb-d4c2-44f0-9467-49daee85ba2b
author: robstackmsft
---
# Choose the right Microsoft Intune policy to use - deleted
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**policies** are groups of settings that control features on mobile devices and computers. You create policies using templates that contain recommended or customized settings, and then deploy them to device or user groups.

## <a name="BKMK_WhatPol"></a>What policies are available?
Use this list to help you decide which policy you need:

### Android

|Policy name|Use when you want to|
|---------------|------------------------|
|**Custom Configuration (Android 4 and later, Samsung KNOX Standard 4.0 and later)**|-   Deploy OMA-URI settings, such as Wi-Fi settings that can be used to control device features. This is useful when the setting you need is not available in a configuration policy.<br /><br />For details, see [Android custom policy settings in Microsoft Intune](../Topic/Android-custom-policy-settings-in-Microsoft-Intune.md).|
|**Email Profile (Samsung KNOX Standard 4.0 and later)**|-   Create, deploy and monitor Exchange ActiveSync email settings on managed devices. This lets users access corporate email on their personal devices without any required setup on their part.<br /><br />For details, see [Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md).|
|**General Configuration (Android 4 and later, Samsung KNOX Standard 4.0 and later)**|-   Configure mobile device security and functional settings.<br />-   Specify apps that are compliant or noncompliant, and report when they are used.<br />-   Configure kiosk mode that locks devices to allow only certain features to work, for example, allow the device to run only one app, or disable the volume buttons.<br /><br />For details, see [Android configuration policy settings in Microsoft Intune](../Topic/Android-configuration-policy-settings-in-Microsoft-Intune.md).|
|**PKCS #12 (.PFX) Certificate Profile (Android 4 and later)**|-   Use this profile to create and deploy PFX settings for device certificate requests.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**SCEP Certificate Profile (Android 4 and later)**|-   Configure a Simple Certificate Enrollment Protocol certificate which can be used with a trusted mobile device certificate to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**Trusted Certificate Profile (Android 4 and later)**|-   Configure a trusted mobile device certificate which can be used to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**VPN Profile (Android 4 and later)**|-   Configure and deploy settings that give users secure access to your company network from their mobile device. By deploying these settings, you minimize the end-user effort required to connect to their work.<br /><br />For details, see [Help users connect to their work using VPN profiles with Microsoft Intune](../Topic/Help-users-connect-to-their-work-using-VPN-profiles-with-Microsoft-Intune.md).|
|**Wi-Fi Profile (Android 4 and later)**|-   Configure and deploy wireless network settings to users in your organization. By deploying these settings, you minimize the end-user effort required to connect to the wireless network.<br /><br />For details, see [Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](../Topic/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md).|

### iOS

|Policy name|Use when you want to|
|---------------|------------------------|
|**Custom Configuration (iOS 7.1 and later)**|-   Deploy configuration profiles to iOS devices that you created using the Apple Configurator tool. This is useful when the setting you need is not available in a configuration policy.<br /><br />For details, see [iOS custom policy settings in Microsoft Intune](../Topic/iOS-custom-policy-settings-in-Microsoft-Intune.md).|
|**Email Profile (iOS 7.1 and later)**|-   Create, deploy and monitor Exchange ActiveSync email settings on managed devices. This lets users access corporate email on their personal devices without any required setup on their part.<br /><br />For details, see [Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md).|
|**General Configuration (iOS 7.1 and later)**|-   Configure mobile device security and functional settings.<br />-   Specify apps that are compliant or noncompliant, and report when they are used.<br />-   Configure kiosk mode that locks devices to allow only certain features to work, for example, allow the device to run only one app, or disable the volume buttons.<br /><br />For details, see [iOS configuration policy settings in Microsoft Intune](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md).|
|**SCEP Certificate Profile (iOS 7.1 and later)**|-   Configure a Simple Certificate Enrollment Protocol certificate which can be used with a trusted mobile device certificate to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**Trusted Certificate Profile (iOS 7.1 and later)**|-   Configure a trusted mobile device certificate which can be used to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**VPN Profile (iOS 7.1 and later)**|-   Configure and deploy settings that give users secure access to your company network from their mobile device. By deploying these settings, you minimize the end-user effort required to connect to their work.<br /><br />For details, see [Help users connect to their work using VPN profiles with Microsoft Intune](../Topic/Help-users-connect-to-their-work-using-VPN-profiles-with-Microsoft-Intune.md).|
|**Wi-Fi Profile (iOS 7.1 and later)**|-   Configure and deploy wireless network settings to users in your organization. By deploying these settings, you minimize the end-user effort required to connect to the wireless network.<br /><br />For details, see [Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](../Topic/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md).|

### Windows
Applies to Windows Phone, and enrolled Windows devices only.

|Policy name|Use when you want to|
|---------------|------------------------|
|**Custom Configuration  (Windows 10 Desktop and Mobile and later)**|-   Deploy OMA-URI settings that can be used to control device features. This is useful when the setting you need is not available in a configuration policy.<br />    For a list of available settings, see [Custom URI settings for Windows 10 devices](../Topic/Custom-URI-settings-for-Windows-10-devices.md).<br /><br />For details, see [Windows 10 custom policy settings in Microsoft Intune](../Topic/Windows-10-custom-policy-settings-in-Microsoft-Intune.md).|
|**Custom Configuration (Windows Phone 8.1 and later)**|-   Deploy OMA-URI settings that can be used to control device features. This is useful when the setting you need is not available in a configuration policy.<br /><br />For details, see [Windows Phone custom policy settings in Microsoft Intune](../Topic/Windows-Phone-custom-policy-settings-in-Microsoft-Intune.md).|
|**Email Profile (Windows Phone 8 and later)**|-   Create, deploy and monitor Exchange ActiveSync email settings on managed devices. This lets users access corporate email on their personal devices without any required setup on their part.<br /><br />For details, see [Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md).|
|**General Configuration (Windows 10 Desktop and Mobile and later)**|-   Configure mobile device security and functional settings for enrolled Windows 10 desktop and Mobile devices.<br /><br />For details, see [Windows 10 configuration policy settings in Microsoft Intune](../Topic/Windows-10-configuration-policy-settings-in-Microsoft-Intune.md).|
|**General Configuration (Windows 8.1 and later)**|-   Configure mobile device security and functional settings for enrolled Windows devices.<br /><br />For details, see [Windows configuration policy settings in Microsoft Intune](../Topic/Windows-configuration-policy-settings-in-Microsoft-Intune.md).|
|**General Configuration (Windows Phone 8.1 and later)**|-   Configure mobile device security and functional settings.<br />-   Specify apps that users can, or cannot use and block noncompliant apps from being installed or used.<br /><br />For details, see [Windows Phone configuration policy settings in Microsoft Intune](../Topic/Windows-Phone-configuration-policy-settings-in-Microsoft-Intune.md).|
|**PKCS #12 (.PFX) Certificate Profile (Windows 10 Desktop and Mobile and later)**|-   Use this profile to create and deploy PFX settings for device certificate requests.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**SCEP Certificate Profile (Windows 8.1 and later)**<br /><br />**SCEP Certificate Profile (Windows Phone 8.1 and later)**|-   Configure a Simple Certificate Enrollment Protocol certificate which can be used with a trusted mobile device certificate to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**Trusted Certificate Profile (Windows 8.1 and later)**<br /><br />**Trusted Certificate Profile (Windows Phone 8.1 and later)**|-   Configure a trusted mobile device certificate which can be used to authenticate mobile devices to allow them to access network resources such as those configured by Wi-Fi and VPN profiles.<br /><br />For details, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|
|**VPN Profile (Windows 10 Desktop and Mobile and later)**<br /><br />**VPN Profile (Windows 8.1 and later)**<br /><br />**VPN Profile (Windows Phone 8.1 and later)**|-   Configure and deploy settings that give users secure access to your company network from their mobile device. By deploying these settings, you minimize the end-user effort required to connect to their work.<br /><br />For details, see [Help users connect to their work using VPN profiles with Microsoft Intune](../Topic/Help-users-connect-to-their-work-using-VPN-profiles-with-Microsoft-Intune.md).|
|**Windows Wi-Fi Import Policy**|-   Import and deploy Windows Wi-Fi configurations that you have previously exported to a file.<br /><br />For details, see [Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](../Topic/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md).|

### Software

|Policy name|Use when you want to|
|---------------|------------------------|
|**Managed Browser Policy (Android 4 and later)**<br /><br />**Managed Browser Policy (iOS 7 and later)**|-   Specify the websites that users can, and cannot access when they are using the managed browser app.<br /><br />For details, see [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).|
|**Mobile Application Management Policy (Android 4 and later)**<br /><br />**Mobile Application Management Policy (iOS 7 and later)**|-   Modify the functionality of apps that you deploy to help bring them into line with your company compliance and security policies. For example, you can restrict cut, copy and paste operations within a restricted app, or configure an app to open all web links inside the managed browser.<br /><br />For details, see [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md)|

### Common Mobile Device Settings

|Policy name|Use when you want to|
|---------------|------------------------|
|**Exchange ActiveSync Policy**|-   Configure mobile device security and functional settings for devices that are managed by Exchange ActiveSync.<br /><br />For details, see [Exchange ActiveSync policy settings in Microsoft Intune](../Topic/Exchange-ActiveSync-policy-settings-in-Microsoft-Intune.md).|
|**Mobile Device Security Policy**|<ul><li>Configures settings for mobile devices (all platforms) including:<br /><br /><ul><li>Security</li><li>Encryption</li><li>System</li><li>Email</li><li>Applications</li></ul></li></ul> **Important:** [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] now features separate **configuration policies** for each device platform, and these policies contain the most up-to-date settings you can use. You can continue to use the mobile device security policy and any existing deployments will still work, but you should plan to migrate to the new configuration policies as soon as possible.<br />For details, see [Mobile device security policy settings in Microsoft Intune](../Topic/Mobile-device-security-policy-settings-in-Microsoft-Intune.md).|

### Conditional access and compliance policies

#### Conditional Access

|Policy name|Use when you want to|
|---------------|------------------------|
|**Exchange Online Policy**<br /><br />**Exchange On-premises Policy**|-   Manage access to Microsoft Exchange email from devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or not compliant with a compliance policy you created.<br /><br />For details, see [Manage email access with Microsoft Intune](../Topic/Manage-email-access-with-Microsoft-Intune.md).|
|**SharePoint Online Policy**|-   Manage access to SharePoint Online from devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or not compliant with a compliance policy you created.<br /><br />For details, see [Manage SharePoint Online access with Microsoft Intune](../Topic/Manage-SharePoint-Online-access-with-Microsoft-Intune.md).|
> [!NOTE]
> You do not deploy conditional access policies to users and devices. Instead, you configure the required policy and it applies to all groups targeted in the policy.

#### Compliance Policies

|Policy name|Use when you want to|
|---------------|------------------------|
|**Compliance policies**|-   Define the level of compliance for devices and then report about devices that are noncompliant. These policies are used with conditional access to help evaluate devices that should be blocked from services.<br /><br />For details, see [Manage device compliance policies for Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md).|

### Computer Management

|Policy name|Use when you want to|
|---------------|------------------------|
|**Microsoft Intune Agent Settings**|Configure the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] client on computers, including settings for:<br /><br />-   Endpoint Protection<br />-   Software updates<br />-   Policy check schedule<br /><br />This type of policy can be deployed only to groups of devices.<br /><br />[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients download new and updated policy according to the **Update and application detection frequency** setting, which defaults to 8 hours. However, you can force a refresh of policy on computers at any time.<br /><br />For details, see [Keep Windows PCs up to date with software updates in Microsoft Intune](../Topic/Keep-Windows-PCs-up-to-date-with-software-updates-in-Microsoft-Intune.md).|
|**Microsoft Intune Center Settings**|Configure details that appear in the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Center on managed computers.<br /><br />This type of policy can be deployed only to groups of devices.<br /><br />For details, see [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md).|
|**Windows Firewall Settings**|Configures Windows Firewall settings and exceptions for common network communications on computers, including:<br /><br />-   BranchCache<br />-   Remote Assistance<br />-   Media sharing<br /><br />This type of policy can be deployed only to groups of devices.<br /><br />For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).|

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical-reference-for-Microsoft-Intune.md)

