---
# required metadata

title: Intune glossary | Microsoft Intune
description: Learn about some of the terminology in Microsoft Intune
keywords:
author: robstackmsft
manager: angrobe
ms.date: 09/23/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: angrobe
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune glossary

## A

|||
|-|-|
|App SDK|The [Microsoft Intune App SDK](/intune/develop/intune-app-sdk) lets you add functionality to your in-house written apps that enables them to be managed by Intune mobile application management policies.|
|App Wrapping Tool|A [command line application](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) that creates a wrapper around a line of business app, which then allows the app to be managed by an Intune mobile application management policy.|
|Available install|When you deploy an app with this action, it is displayed in the company portal, and users can [install it on demand](/intune/deploy-use/deploy-apps).|
|Azure Portal|A new console for Intune which will be introduced soon. At the moment, you can use the Azure portal to create [Intune MAM policies](/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) for devices.|

## B
|||
|-|-|
|BYOD|[Bring your own device](/intune/get-started/choose-how-to-enroll-devices1). Users can install the Intune Company Portal app on their device and then enroll it, gaining access to company resources like email, company apps, company data, and support.| 

## C
|||
|-|-|
|Certificate profile|You use this policy type to [secure access to corporate resources](/intune/deploy-use/secure-resource-access-with-certificate-profiles) with certificates when you use Wi-Fi, email, or VPN profiles.|
|Cloud storage space|A place where apps, or the data about apps you create [is stored](/intune/deploy-use/add-apps#cloud-storage-space).|
|COD|[Company owned devices](/intune/get-started/choose-how-to-enroll-devices1) can be enrolled in a variety of ways, depending upon the needs of the organization and the types of devices being managed.|
|Company Portal|An app or a website that provides users with [access to company data and apps](/intune/get-started/microsoft-intune-company-portal).|
|Compliance policy|Makes sure that the devices used to access company apps and data, [comply with certain rules ](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)like using a PIN to access the device, and encryption of data stored on the device.|
|Compliant and noncompliant apps|Part of a [general configuration policy](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), these settings let you define a list of apps that users can, or cannot run. Intune will then inform you via. reports that a noncompliant app was installed, or run. For some platforms, Intune can also block install of a noncompliant app.|
|Conditional access|[Allows access to company email, Office 365, and other  services](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) only from devices that are compliant with rules you set.|
|Custom policy|You [use these policies](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) when a general configuration policy does not contain a built-in setting that meets your needs. You might be able to use a custom policy to create a setting by other means like the Apple Configurator, or OMA-URI.|

## D
|||
|-|-|
|Deployment|The act of sending an app or a policy to a device or user you manage.|
|Deployment action|A choice you make when you [deploy an app](/intune/deploy-use/deploy-apps-in-microsoft-intune). You can choose to make the app installation mandatory, optional, or you can uninstall the app.|
|Device enrollment manager|Organizations can use Intune to manage large numbers of mobile devices with a single user account. The [device enrollment manager (DEM)](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) account is a special Intune account that can enroll up to 1,000 devices.|
|Device group mapping|Helps you to [automatically add devices to groups](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) based on a category of device (like "Personal", or "Sales") that you, or the end user can assign to the device.|

## E
|||
|-|-|
|Email profile|This policy can be used to set up [email access settings](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) for specific email clients on mobile devices minimizing the amount of setup the end user has to do.|
|EMS|Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) keeps your company data protected while enabling your users to [access the apps and content they need](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility).|
|End user|[Users of devices like phones and PCs](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) that you manage using Intune.|
|Enroll|Microsoft Intune uses [enrollment](/intune/deploy-use/enroll-devices-in-microsoft-intune) to bring devices into management and allow access to resources.|

## F
|||
|-|-|
|FastTrack|A [Microsoft service](https://technet.microsoft.com/library/mt228265.aspx) for Intune users with 150 licenses in an eligible plan. Using this service, Microsoft specialists will work with you to get up and running with Intune.|

## G
|||
|-|-|
|Groups|Groups let you [logically collect together users or devices](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). For example, you might create a group of all Windows PCs. You can then deploy apps and policy to these groups.|

## H
|||
|-|-|
|Hybrid|A configuration where you can manage devices that are enrolled with Intune [through the System Center Configuration Manager console](/intune/get-started/integration-with-cloud-services).|

## I
|||
|-|-|
|Intune administration console|The current console you use for most Intune management operations.|
|Intune software client|An alternative way of [managing some Windows PCs](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). See [Choose how to manage devices](/intune/get-started/choose-how-to-manage-devices) for help deciding which method to use.|
|Intune Software Publisher|A tool you use to [define apps you want to deploy and upload them to your cloud storage space](/intune/deploy-use/add-apps).|
|Inventory|Use to view the [hardware of, and the software installed](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) on devices you manage.|

## K
|||
|-|-|
|Kiosk mode|Configured as part of a [general configuration policy](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), this mode lets you lock down devices. For example, you could configure a retail device to only allow one app to run.|

## M
|||
|-|-|
|Managed Browser|A [web browsing application](/intune/deploy-use/manage-internet-access-using-managed-browser-policies) that you can deploy in your organization by using Microsoft Intune. A managed browser policy configures an allow list or a block list that restricts the websites that users of the managed browser can visit.|
|Mobile application management|[Mobile application management (MAM)](/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) lets you publish, push, configure, secure, monitor, and update mobile apps for your users.
|Mobile device management|[Mobile device management (MDM)](/intune/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) lets you enroll devices in Intune so that you can provision, configure, monitor, and take actions on those devices. 
|MDM authority|The [MDM authority](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) defines the management service that has permission to manage a set of devices. The options for the MDM authority include Intune by itself and Configuration Manager with Intune.|
|Mobile app provisioning policy|An iOS policy that helps you ensure that [provisioning profiles](/intune/deploy-use/ios-mobile-app-provisioning-profiles) for iOS apps you deploy do not expire.|
|Mobile app configuration policy|An iOS policy that is used to [supply settings to compatible iOS apps](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) when they are run, for example, a company name, or server address.|

## O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. An industry standard device management protocol used by many hardware manufacturers to enable control of features of mobile devices and PCs.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. These identify individual device settings that conform to the OMA-DM standard. A number of these can be used in [Intune custom policies](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) when there is no built-in setting to meet your needs.|

## P
|||
|-|-|
|Policy|A [package of information](/intune/deploy-use/microsoft-intune-policy-reference) sent from Intune to a device. For example, you could deploy security settings, or device compliance information to the device.|
|Passcode reset|An Intune feature that lets you force the end user to [reset the passcode](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) on supported devices.|

## R
|||
|-|-|
|Remote lock|An Intune feature that lets you [lock supported devices](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), even if you are not in possession of the device.|
|Reports|Intune provides a range of [built-in reports](/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) that give you information about the devices you manage.|
|Required install|When you deploy an app with this action, it is installed on the device with [no user intervention](/intune/deploy-use/deploy-apps) (although for some platforms, the end user might have to accept the installation).|
|Requirements|An [app deployment operation](/en-us/intune/deploy-use/add-apps) that lets you select the requirements that must be met on a device before the app is installed. For example, you could specify the OS version of iOS that must be installed before the app gets installed.|

## S
|||
|-|-|
|Selective wipe|A [selective wipe](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) removes only company data including mobile app management (MAM) data where applicable, settings, and email profiles from a device. Selective wipe leaves the user's personal data on the device.|

## T
|||
|-|-|
|TeamViewer|A third-party application that works with Intune to provide [remote assistance capabilities](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) for Windows PCs managed with the Intune software client.|
|Terms and conditions|A policy type you deploy to users that contains information users must [read and accept](/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) before they can use the Company Portal to enroll and access their work.|

## V
|||
|-|-|
|Volume-purchased app|Some app stores give you the ability to purchase multiple licenses for an app that you want to run in your company. Intune helps you manage apps that you [purchased through such a program](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune) by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.|
|VPN profile|A policy that deploys [VPN settings](/intune/deploy-use/vpn-connections-in-microsoft-intune) to devices you manage, minimizing any setup required for end users.|

## W
|||
|-|-|
|Wi-Fi profile|A policy that deploys [wireless network settings](/intune/deploy-use/wi-fi-connections-in-microsoft-intune) to devices to let users connect to your company network without needing to know, or configure any settings.



