---
title: Mobile device management capabilities in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
author: robstackmsft
---

[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] lets you manage a range of devices by *enrolling* them into the service. Users can then use a *company portal* to perform a range of operations such as enrolling their device, browsing and installing apps, making sure their device is compliant with company policies, and contacting their IT support.
See later in this topic for a full list of the capabilities that enrolling devices gives you.

Management, inventory, app deployment, provisioning, and retirement are all handled through the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] administration console. Users gain access to the company portal which allows them to install apps, enroll and remove devices, and helps them contact their IT department or helpdesk.



## Device security and configuration

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Configuration policies<br><br>Custom policies|Mobile device configuration policies let you manage many settings and features on mobile devices in your organization. For example, you can you require a password, limit the number of failed attempts, limit the minutes before the screen locks, set password expiration, and prevent previously-used passwords. You could also control the use of hardware and software features such as the device camera, or the web browser<br><br>Use custom polices when configuration policies do not contain the setting you require. For iOS devices, you can import settings you exported from the Apple Configurator Tool. For other devices, you can use OMA-URI settings to configure settings and features on the device.|[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)<br />|
|Remote Wipe, Remote Lock, and Passcode Reset|Erase sensitive data when a device is lost or stolen. For example, you can remotely lock the device, restore it to factory settings, or wipe only corporate data.<br>You can reset passcodes if users lose access to their device, lock missing or stolen devices, or even wipe data off of missing or stolen devices.|[Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-microsoft-intune.md)|
|Kiosk mode|Lets you lock down certain features of mobile devices such as screen capture and the power switch. Also lets you restrict devices to run a single app that you specify.|[iOS configuration policy settings in Microsoft Intune](ios-configuration-policy-settings-in-microsoft-intune.md)|

## App management

|Capability|Details|More information|
|--------------|-----------|--------------------|
|App deployment and management|Provides a range of tools to help you manage mobile apps through their lifecycle, including app deployment from installation files and app stores, detailed monitoring of app status, and app removal.|[Deploy apps to mobile devices in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md)|
|Compliant and noncompliant apps|Lets you specify lists of compliant apps (that users are allowed to install) and noncompliant apps (which must not be installed by users).|[iOS configuration policy settings in Microsoft Intune](ios-configuration-policy-settings-in-microsoft-intune.md)|
|Mobile application management|Configure restrictions for apps by using mobile application management for both devices you manage with Intune, and also devices that are not managed by Intune. This helps you to increase the security of your company data by restricting operations such as copy and paste, external backup of data and the transfer of data between apps.|[Configure and deploy mobile application management policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)<br><br>[Configure data loss prevention app policies with Microsoft Intune](configure-data-loss-prevention-app-policies-with-microsoft-intune.md)<br /><br />[Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)<br /><br />[Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)|
|Mobile app configuration|Use mobile app configuration policies to supply settings for iOS apps that might be required when the user runs the app. For example, an app might require the user to specify a port number of logon information. This can help streamline app configuration and reduce the number of help desk calls.|[Configure apps with mobile app configuration policies in Microsoft Intune](configure-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)|
|Managed browser|After you deploy the managed browser to your users, you can configure a managed browser policy to control the websites that they can visit. In addition, you can also apply mobile application management policies to the managed browser.|[Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies-with-microsoft-intune.md)|
|Microsoft Passport|Intune lets you integrate with Microsoft Passport for Work which is an alternative sign-in method for Windows 10 that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.|[Control Microsoft Passport settings on devices with Microsoft Intune](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)|

## Company resource access

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Certificate profiles|Create and deploy trusted certificate profiles and Simple Certificate Enrollment Protocol (SCEP) certificates which can be used to help secure and authenticate Wi-Fi, VPN, and email profiles.|[Enable access to company resources using certificate profiles with Microsoft Intune](enable-access-to-company-resources-using-certificate-profiles-with-microsoft-intune.md)|
|Wi-Fi profiles|Deploy wireless network settings to your users. By deploying these settings, you minimize the end-user effort required to connect to the corporate network.|[Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](help-users-connect-to-company-networks-using-wi-fi-profiles-with-microsoft-intune.md)|
|Email profiles|Create and deploy email settings to devices. This lets users access corporate email on their personal devices without any required setup on their part.|[Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profiles|Deploy VPN settings to users and devices in your organization. By deploying these settings, you minimize the end-user effort required to connect to resources on the company network.|[Help users connect to their work using VPN profiles with Microsoft Intune](help-users-connect-to-their-work-using-vpn-profiles-with-microsoft-intune.md)|
|Conditional access policies|Manage access to Microsoft Exchange email and SharePoint Online from devices that are not managed by [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].|[Manage access to email and SharePoint with Microsoft Intune](manage-access-to-email-and-sharepoint-with-microsoft-intune.md)|

## Inventory and reporting

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Inventory and reporting|Find information about the devices you manage and the software they are using.<br /><br />You can filter these reports in a number of ways, such as the device platform, and whether the device is compliant with corporate standards.|[Understand Microsoft Intune operations by using reports](understand-microsoft-intune-operations-by-using-reports.md)|



