---
# required metadata

title: Enrolled device management capabilities 
description: Read this topic to find out how Intune can help you manage devices that you enroll.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---
# Enrolled device management capabilities of Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune lets you manage a range of devices by *enrolling* them into the service. You can enroll some device types yourself, or users can enroll using the *company portal* app. This also lets them perform operations like browsing and installing apps, ensuring that their devices are compliant with company policies, and contacting their IT support.

This topic gives a full list of the capabilities that you get after you enroll your device.

Management, inventory, app deployment, provisioning, and retirement are all handled through the Intune administration console. Users gain access to the company portal, which enables them to install apps, enroll and remove devices, and contact their IT department or helpdesk.



## Device security and configuration

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Configuration policies<br><br>Custom policies| Lets you manage many settings and features on mobile devices in your organization. For example, you can  require a password, limit the number of failed attempts, limit the amount of time before the screen locks, set password expiration, and prevent previously used passwords. You can also control the use of hardware and software features such as the device camera or the web browser.<br><br>Use custom polices when configuration policies do not contain the settings that you require. For iOS devices, you can import settings that you exported from the Apple Configurator tool. For other devices, you can use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to configure settings and features on the device.|[Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Remote Wipe, Remote Lock, and Passcode Reset|Erases sensitive data when a device is lost or stolen. For example, you can remotely lock the device, restore it to factory settings, or wipe only corporate data.<br><br>You can reset passcodes if users lose access to their device, lock missing or stolen devices, or even wipe data off of missing or stolen devices.|[Help protect your devices with remote lock and passcode reset](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Kiosk mode|Lets you lock down certain features of mobile devices such as screen captures and power switches. Also lets you restrict devices to run a single app that you specify.|[iOS configuration policy settings in Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## App management

|Capability|Details|More information|
|--------------|-----------|--------------------|
|App deployment and management|Provides a range of tools to help you manage mobile apps through their lifecycle, including app deployment from installation files and app stores, detailed monitoring of app status, and app removal.|[Deploy apps in Microsoft Intune](/intune-classic/deploy-use/deploy-apps)|
|Compliant and noncompliant apps|Lets you specify lists of compliant apps (that users are allowed to install) and noncompliant apps (that users aren't allowed to install).|[iOS policy settings in Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobile application management|Configures restrictions for apps by using mobile application management for all devices that are both managed with Intune and not managed with Intune. This helps you to increase the security of your company data by restricting operations such as copy and paste, external backup of data, and the transfer of data between apps.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/app-wrapper-prepare-android)|
|iOS mobile app configuration|Uses mobile app configuration policies to supply settings for iOS apps that might be required when the user runs the app. For example, an app might require the user to specify a port number or logon information. This can help streamline app configuration and reduce the number of support calls.|[Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS mobile app provisioning profiles|Helps you deploy provisioning profiles to iOS apps that are nearing expiration. |[Use iOS mobile provisioning profile policies to prevent your apps from expiring](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Managed browser|Configures managed browser policies to control the websites that device users can visit. In addition, you can also apply mobile application management policies to the managed browser.|[Manage Internet access using managed browser policies with Microsoft Intune](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello for Business|Lets you integrate with Windows Hello for Business, which is an alternative sign-in method for Windows 10 that uses on-premises Active Directory or  Azure Active Directory to replace passwords, smart cards, or virtual smart cards.|[Control Windows Hello for Business settings on devices with Microsoft Intune](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Volume purchased apps|Helps you manage apps that you purchased through a volume-purchase program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.|[Manage volume-purchased apps using Microsoft Intune](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## Company resource access

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Certificate profiles|Creates and deploys trusted certificate profiles and Simple Certificate Enrollment Protocol (SCEP) certificates, which can be used to secure and authenticate Wi-Fi, VPN, and email profiles.|[Secure resource access with certificate profiles in Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi profiles|Deploys wireless network settings to your users. By deploying these settings, you minimize the user effort that's required to connect to the corporate network.|[Wi-Fi connections in Microsoft Intune](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|Email profiles|Creates and deploys email settings to devices. This means that users can access corporate email on their personal devices without any required setup on their part.|[Configure access to corporate email using email profiles with Microsoft Intune](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profiles|Deploys VPN settings to users and devices in your organization. By deploying these settings, you minimize the user effort that's required to connect to resources on the company network.|[VPN connections in Microsoft Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Conditional access policies|Manages access to Microsoft Exchange email and SharePoint Online from devices that are not managed by Intune.|[Restrict access to email and SharePoint with Microsoft Intune](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventory and reporting

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Inventory and reporting|Finds information about the devices that you manage and the software that the devices are using.|[Understand your devices with inventory in Microsoft Intune](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|
