---
# required metadata

title: Mobile device management capabilities | Microsoft Intune
description: Read this topic to find out how Intune can help you manage your mobile devices that you enroll with the service.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Mobile device management capabilities of Microsoft Intune

Microsoft Intune lets you manage a range of devices by *enrolling* them into the service. You can enroll some device types yourself, or users can enroll using the *company portal* app. This also lets them perform operations like browsing and installing apps, ensuring that their devices are compliant with company policies, and contacting their IT support.

This topic gives a full list of the capabilities that you get after you enroll your device.

Management, inventory, app deployment, provisioning, and retirement are all handled through the Intune administration console. Users gain access to the company portal, which enables them to install apps, enroll and remove devices, and contact their IT department or helpdesk.



## Device security and configuration

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Configuration policies<br><br>Custom policies| Lets you manage many settings and features on mobile devices in your organization. For example, you can  require a password, limit the number of failed attempts, limit the amount of time before the screen locks, set password expiration, and prevent previously used passwords. You can also control the use of hardware and software features such as the device camera or the web browser.<br><br>Use custom polices when configuration policies do not contain the settings that you require. For iOS devices, you can import settings that you exported from the Apple Configurator tool. For other devices, you can use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to configure settings and features on the device.|[Manage settings and features on your devices with Microsoft Intune policies](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Remote Wipe, Remote Lock, and Passcode Reset|Erases sensitive data when a device is lost or stolen. For example, you can remotely lock the device, restore it to factory settings, or wipe only corporate data.<br><br>You can reset passcodes if users lose access to their device, lock missing or stolen devices, or even wipe data off of missing or stolen devices.|[Help protect your devices with remote lock and passcode reset](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) and [Retire devices from Intune management](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Kiosk mode|Lets you lock down certain features of mobile devices such as screen captures and power switches. Also lets you restrict devices to run a single app that you specify.|[iOS configuration policy settings in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## App management

|Capability|Details|More information|
|--------------|-----------|--------------------|
|App deployment and management|Provides a range of tools to help you manage mobile apps through their lifecycle, including app deployment from installation files and app stores, detailed monitoring of app status, and app removal.|[Deploy apps in Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Compliant and noncompliant apps|Lets you specify lists of compliant apps (that users are allowed to install) and noncompliant apps (that users aren't allowed to install).|[iOS policy settings in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobile application management|Configures restrictions for apps by using mobile application management for all devices that are both managed with Intune and not managed with Intune. This helps you to increase the security of your company data by restricting operations such as copy and paste, external backup of data, and the transfer of data between apps.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Create and deploy mobile app management policies with Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|iOS mobile app configuration|Uses mobile app configuration policies to supply settings for iOS apps that might be required when the user runs the app. For example, an app might require the user to specify a port number or logon information. This can help streamline app configuration and reduce the number of support calls.|[Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS mobile app provisioning profiles|Helps you deploy provisioning profiles to iOS apps that are nearing expiration. |[Use iOS mobile provisioning profile policies to prevent your apps from expiring](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|Managed browser|Configures managed browser policies to control the websites that device users can visit. In addition, you can also apply mobile application management policies to the managed browser.|[Manage Internet access using managed browser policies with Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Lets you integrate with Microsoft Passport for Work, which is an alternative sign-in method for Windows 10 that uses on-premises Active Directory or  Azure Active Directory to replace a passwords, smart cards, or virtual smart cards.|[Control Microsoft Passport settings on devices with Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Company resource access

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Certificate profiles|Creates and deploys trusted certificate profiles and Simple Certificate Enrollment Protocol (SCEP) certificates, which can be used to secure and authenticate Wi-Fi, VPN, and email profiles.|[Secure resource access with certificate profiles in Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi profiles|Deploys wireless network settings to your users. By deploying these settings, you minimize the user effort that's required to connect to the corporate network.|[Wi-Fi connections in Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Email profiles|Creates and deploys email settings to devices. This means that users can access corporate email on their personal devices without any required setup on their part.|[Configure access to corporate email using email profiles with Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profiles|Deploys VPN settings to users and devices in your organization. By deploying these settings, you minimize the user effort that's required to connect to resources on the company network.|[VPN connections in Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Conditional access policies|Manages access to Microsoft Exchange email and SharePoint Online from devices that are not managed by Intune.|[Restrict access to email and SharePoint with Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventory and reporting

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Inventory and reporting|Finds information about the devices that you manage and the software that the devices are using.|[Understand your devices with inventory in Microsoft Intune](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### See also
[Windows PC management capabilities in Microsoft Intune](windows-pc-management-capabilities-in-microsoft-intune.md)
