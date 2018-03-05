---
# required metadata

title: Microsoft Intune glossary
titleSuffix: Microsoft Intune
description: Learn the meanings of the terminology used in Microsoft Intune.
keywords:
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 07/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: angrobe
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Microsoft Intune glossary
Learn the definitions of common terms used throughout Microsoft Intune.

## A

|||
|-|-|
|App assignment|Lets users [find, download, and install](/intune/app-management) the apps they need. This was previously known as *app deployment*.|
|App configuration profile <br/><br/>App configuration policy|Available to mobile apps with vendor-specific configurations. Configures an [iOS](/intune/app-configuration-policies-use-ios) or [Android](/intune/app-configuration-policies-use-android) app with specific settings before it runs.|
|App monitoring|Lets you [review recent status and activity](/intune/apps-monitor) related to app assignment.|
|App protection data removal task|[Removes app data](/intune/app-protection-policies) from the user's device.|
|App protection policy|Available to mobile apps that integrate with Enterprise Mobility + Security (EMS) technologies. Ensures that user's apps are compliant with your [company data protection policies](/intune/app-protection-policies).|
|App SDK|The [Microsoft Intune App SDK](/intune/app-sdk) lets you add functionality to your in-house written apps that enables them to be managed by Intune app protection policies.|
|App uninstall action|Lets you [uninstall apps](/intune/apps-deploy) from user's devices.|
|App Wrapping Tool|A [command-line application](/intune/apps-prepare-mobile-application-management) that creates a wrapper around a line-of-business app, letting it be managed by an Intune app protection policy.|
|Assignment action|A choice you make when you [assign an app](/intune/apps-deploy). You can choose to make the app installation mandatory (required), optional (Available), or you can uninstall the app.|
|Available install|When you assign an app with this action, it is displayed in the company portal, and users can [install it on demand](/intune/apps-deploy).|
|Azure Portal|The new console for Intune [Read more](/intune/what-is-intune).|

## B
|||
|-|-|
|BYOD|[Bring your own device](/intune/device-enrollment). Users can install the Intune Company Portal app on their device and then enroll it, gaining access to company resources like email, company apps, company data, and support.|

## C
|||
|-|-|
|Certificate profile|You use this policy type to [secure access to corporate resources](/intune/certificates-configure) with certificates when you use Wi-Fi, email, or VPN profiles.|
|COD|[Company owned devices](/intune/device-enrollment) can be enrolled in numerous ways, depending upon the needs of the organization and the types of devices being managed.|
|Company Portal|An app or a website that provides users with [access to company data and apps](/intune/company-portal-customize).|
|Compliance policy|Makes sure that the devices [comply with certain rules ](/intune/device-compliance) like using a PIN to access the device, and encryption of data stored on the device.|
|Compliant and noncompliant apps|Part of a [device restriction profile](/intune/device-restrictions-configure), these settings let you define a list of apps that users can, or cannot run. Intune then informs you via. reports that a noncompliant app was installed, or run. For some platforms, Intune can also block install of a noncompliant app.|
|Conditional access|[Allows access to company email, Office 365, and other  services](/intune/conditional-access) only from devices that are compliant with rules you set.|
|Custom policy|You [use these policies](/intune/custom-settings-configure) when a general configuration policy does not contain a built-in setting that meets your needs. You might be able to use a custom policy to create a setting by other means like the Apple Configurator, or OMA-URI.|

## D
|||
|-|-|
|Deployment|The act of sending an app or a policy to a device or user you manage. This action is now known as *assign*.|
|Device enrollment manager|Organizations can use Intune to manage large numbers of mobile devices with a single user account. The [device enrollment manager (DEM) account](/intune/device-enrollment-program-enroll-ios) is a special Intune account that can enroll up to 1,000 devices.|
|Device profiles|[These profiles](/intune/device-profile-create) let you configure a wide range of security, feature, and access settings on devices you manage.|

## E
|||
|-|-|
|Email profile|This policy can be used to set up [email access settings](/intune/email-settings-configure) for on mobile devices, minimizing the amount of setup the end user must do.|
|EMS|Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) keeps your company data protected while enabling your users to [access the apps and content they need](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|End user|[Users of devices like phones and PCs](/intune/end-user-educate) that are managed using Intune.|
|Enroll|Microsoft Intune uses [enrollment](/intune/device-enrollment) to bring devices into management and allow access to resources.|

## F
|||
|-|-|
|FastTrack|A [Microsoft service](https://technet.microsoft.com/library/mt228265.aspx) for Intune users with 150 licenses in an eligible plan. Using this service, Microsoft specialists can work with you to get up and running with Intune.|

## G
|||
|-|-|
|Groups|Groups let you [logically collect together users or devices](/intune/groups-get-started). For example, you might create a group of all Windows PCs. You can then assign apps and profiles to these groups.|

## H
|||
|-|-|
|Hybrid|A configuration where you can manage devices that are enrolled with Intune through the System Center Configuration Manager console.|

## I
|||
|-|-|
|Azure portal|The Azure portal you use for most Intune management operations.|
|Intune software client|An alternative way of [managing some Windows PCs](/intune-classic/get-started/choose-how-to-manage-devices) for help deciding which method to use.|
|Intune Software Publisher|A tool you use to [define apps you want to deploy and upload them to your cloud storage space](/intune-classic/deploy-use/add-apps).|
|Inventory|Use to view the [hardware of, and the software installed](/intune/device-inventory) on devices you manage.|

## K
|||
|-|-|
|Kiosk mode|Configured as part of a [device restriction profile](/intune/device-restrictions-configure), this mode lets you lock down devices. For example, you could configure a retail device to only allow some apps to run.|

## M
|||
|-|-|
|Managed Browser|A [web browsing application](/intune/app-configuration-managed-browser) that you can assign in your organization by using Intune. A managed browser policy configures an allow list or a block list that restricts the websites that users of the managed browser can visit.|
|MDM authority|The [MDM authority](/intune/mdm-authority-set) defines the management service that has permission to manage a set of devices. The options for the MDM authority include Intune by itself and Configuration Manager with Intune.|
|Mobile app configuration policy|Available to mobile apps with vendor-specific configurations. For example, an [iOS](/intune/app-configuration-policies-use-ios) or [Android](/intune/app-configuration-policies-use-android) policy that is used to supply settings to compatible apps when they are run, for example, a company name, or server address.|
|Mobile app provisioning policy|An iOS policy that helps you ensure that [provisioning profiles](/intune/app-provisioning-profile-ios) for iOS apps you assign do not expire.|
|Mobile application management|[Mobile application management (MAM)](/intune/app-lifecycle) lets you publish, push, configure, secure, monitor, and update mobile apps for your users.
|Mobile device management|[Mobile device management (MDM)](/intune/device-lifecycle) lets you enroll devices in Intune so that you can provision, configure, monitor, and manage those devices.



## O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. An industry standard device management protocol used by many hardware manufacturers to enable control of features of mobile devices and PCs.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. These items identify individual device settings that conform to the OMA-DM standard. The settings can be used in [Intune custom profiles](/intune/custom-settings-configure) when there is no built-in setting to meet your needs.|

## P
|||
|-|-|
|Passcode reset|An Intune feature that lets you force the end user to [reset the passcode](/intune/device-passcode-reset) on supported devices.|

## R
|||
|-|-|
|Remote lock|An Intune feature that lets you [lock supported devices](/intune/device-remote-lock), even if you do not possess the device.|
|Required install|When you assign an app with this action, [user intervention](/intune/apps-deploy) is not required to complete the installation. On some platforms, the end user might have to accept the installation).|


## S
|||
|-|-|
|Selective wipe|A [selective wipe](/intune/device-company-data-remove) removes only company data protected by app protection policy including settings and email profiles from a device. Selective wipe leaves the user's personal data on the device.|
|Sideloading|The action of installing a line-of-business app without accessing it from an app store.|
|Subscription|The agreement you enter that allows you to access an Intune tenant.|

## T
|||
|-|-|
|TeamViewer|A third-party application that works with Intune to provide [remote assistance capabilities](/intune/device-profile-android-teamviewer) for Android device that you manage with Intune.|
|Tenant|A single instance of the Intune service you can access with a subscription.|
|Terms and conditions|A policy type you assign to users that contains information users must [read and accept](/intune/terms-and-conditions-create) before they can use the Company Portal to enroll and access their work.|

## V
|||
|-|-|
|Volume-purchased apps and books|Some app stores give you the ability to purchase multiple licenses for an app or book that you want to use in your company. Intune helps you manage apps and books that you [purchased through such a program](/intune/vpp-apps). You can import the license information from the app store, track how many of the licenses you have used, and prevent yourself from installing more copies of the app than you own.|
|VPN profile|A policy that assigns [VPN settings](/intune/vpn-settings-configure) to devices you manage, minimizing any setup required for end users.|

## W
|||
|-|-|
|Wi-Fi profile|A policy that assigns [wireless network settings](/intune/wi-fi-settings-configure) to devices to let users connect to your company network without needing to know, or configure any settings.
