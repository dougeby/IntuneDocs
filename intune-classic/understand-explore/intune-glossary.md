---
# required metadata

title: Intune glossary 
description: Learn about some of the terminology in Microsoft Intune
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 06/16/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
#ms.reviewer: angrobe
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Microsoft Intune glossary

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## A

|||
|-|-|
|App configuration profile|Configures an iOS app with [specific settings](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) before it runs.|
|App deployment|Lets users [find, download, and install](/intune-classic/deploy-use/deploy-apps) the apps they need.|
|App monitoring|Lets you [review recent status and activity](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune) related to app deployment.|
|App protection data removal task|[Removes app data](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) from the user's device.|
|App protection policy|Ensures that user's apps are compliant with your [company data protection policies](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).|
|App reporting|Lets you [review historical data](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports) about app deployment status and activity.|
|App SDK|The [Microsoft Intune App SDK](/intune/app-sdk) lets you add functionality to your in-house written apps that enables them to be managed by Intune mobile application management policies.|
|App uninstall action|Lets you [uninstall apps](/intune-classic/deploy-use/deploy-apps) from user's devices.|
|App Wrapping Tool|A [command line application](/intune/apps-prepare-mobile-application-management) that creates a wrapper around a line of business app, which then allows the app to be managed by an Intune mobile application management policy.|
|Available install|When you deploy an app with this action, it is displayed in the company portal, and users can [install it on demand](/intune-classic/deploy-use/deploy-apps).|
|Azure Portal|The new console for Intune which will be introduced soon. [Read more about the new portal](/intune/what-is-intune).|

## B
|||
|-|-|
|BYOD|[Bring your own device](/intune-classic/get-started/choose-how-to-enroll-devices1). Users can install the Intune Company Portal app on their device and then enroll it, gaining access to company resources like email, company apps, company data, and support.|

## C
|||
|-|-|
|Certificate profile|You use this policy type to [secure access to corporate resources](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) with certificates when you use Wi-Fi, email, or VPN profiles.|
|Cloud storage space|A place where apps, or the data about apps you create [is stored](/intune-classic/deploy-use/add-apps#cloud-storage-space).|
|COD|[Company owned devices](/intune-classic/get-started/choose-how-to-enroll-devices1) can be enrolled in a variety of ways, depending upon the needs of the organization and the types of devices being managed.|
|Company Portal|An app or a website that provides users with [access to company data and apps](/intune-classic/get-started/microsoft-intune-company-portal).|
|Compliance policy|Makes sure that the devices used to access company apps and data, [comply with certain rules ](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)like using a PIN to access the device, and encryption of data stored on the device.|
|Compliant and noncompliant apps|Part of a [general configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), these settings let you define a list of apps that users can, or cannot run. Intune will then inform you via. reports that a noncompliant app was installed, or run. For some platforms, Intune can also block install of a noncompliant app.|
|Conditional access|[Allows access to company email, Office 365, and other  services](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) only from devices that are compliant with rules you set.|
|Custom policy|You [use these policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) when a general configuration policy does not contain a built-in setting that meets your needs. You might be able to use a custom policy to create a setting by other means like the Apple Configurator, or OMA-URI.|

## D
|||
|-|-|
|Deployment|The act of sending an app or a policy to a device or user you manage.|
|Deployment action|A choice you make when you [deploy an app](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune). You can choose to make the app installation mandatory, optional, or you can uninstall the app.|
|Device enrollment manager|Organizations can use Intune to manage large numbers of mobile devices with a single user account. The [device enrollment manager (DEM) account](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) account is a special Intune account that can enroll up to 1,000 devices.|
|Device group mapping|Helps you to [automatically add devices to groups](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) based on a category of device (like "Personal", or "Sales") that you, or the end user can assign to the device.|

## E
|||
|-|-|
|Email profile|This policy can be used to set up [email access settings](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) for specific email clients on mobile devices minimizing the amount of setup the end user has to do.|
|EMS|Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) keeps your company data protected while enabling your users to [access the apps and content they need](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|End user|[Users of devices like phones and PCs](/intune/end-user-educate) that are managed using Intune.|
|Enroll|Microsoft Intune uses [enrollment](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) to bring devices into management and allow access to resources.|

## F
|||
|-|-|
|FastTrack|A [Microsoft service](https://technet.microsoft.com/library/mt228265.aspx) for Intune users with 150 licenses in an eligible plan. Using this service, Microsoft specialists will work with you to get up and running with Intune.|

## G
|||
|-|-|
|Groups|Groups let you [logically collect together users or devices](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). For example, you might create a group of all Windows PCs. You can then deploy apps and policy to these groups.|

## H
|||
|-|-|
|Hybrid|A configuration where you can manage devices that are enrolled with Intune [through the System Center Configuration Manager console](/intune-classic/get-started/integration-with-cloud-services).|

## I
|||
|-|-|
|Intune administration console|The current console you use for most Intune management operations.|
|Intune software client|An alternative way of [managing some Windows PCs](/intune-classic/get-started/choose-how-to-manage-devices) for help deciding which method to use.|
|Intune Software Publisher|A tool you use to [define apps you want to deploy and upload them to your cloud storage space](/intune-classic/deploy-use/add-apps).|
|Inventory|Use to view the [hardware of, and the software installed](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) on devices you manage.|

## K
|||
|-|-|
|Kiosk mode|Configured as part of a [general configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), this mode lets you lock down devices. For example, you could configure a retail device to only allow one app to run.|

## M
|||
|-|-|
|Managed Browser|A [web browsing application](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies) that you can deploy in your organization by using Microsoft Intune. A managed browser policy configures an allow list or a block list that restricts the websites that users of the managed browser can visit.|
|Mobile application management|[Mobile application management (MAM)](/intune/app-lifecycle) lets you publish, push, configure, secure, monitor, and update mobile apps for your users.
|Mobile device management|[Mobile device management (MDM)](/intune/device-lifecycle) lets you enroll devices in Intune so that you can provision, configure, monitor, and take actions on those devices.
|MDM authority|The [MDM authority](/intune-classic/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) defines the management service that has permission to manage a set of devices. The options for the MDM authority include Intune by itself and Configuration Manager with Intune.|
|Mobile app provisioning policy|An iOS policy that helps you ensure that [provisioning profiles](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles) for iOS apps you deploy do not expire.|
|Mobile app configuration policy|An iOS policy that is used to [supply settings to compatible iOS apps](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) when they are run, for example, a company name, or server address.|

## O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. An industry standard device management protocol used by many hardware manufacturers to enable control of features of mobile devices and PCs.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. These identify individual device settings that conform to the OMA-DM standard. A number of these can be used in [Intune custom policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) when there is no built-in setting to meet your needs.|

## P
|||
|-|-|
|Policy|A [package of information](/intune-classic/deploy-use/microsoft-intune-policy-reference) sent from Intune to a device. For example, you could deploy security settings, or device compliance information to the device.|
|Passcode reset|An Intune feature that lets you force the end user to [reset the passcode](/intune-classic/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) on supported devices.|

## R
|||
|-|-|
|Remote lock|An Intune feature that lets you [lock supported devices](/intune-classic/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), even if you are not in possession of the device.|
|Reports|Intune provides a range of [built-in reports](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports) that give you information about the devices you manage.|
|Required install|When you deploy an app with this action, it is installed on the device with [no user intervention](/intune-classic/deploy-use/deploy-apps) (although for some platforms, the end user might have to accept the installation).|
|Requirements|An [app deployment operation](/intune-classic/deploy-use/add-apps) that lets you select the requirements that must be met on a device before the app is installed. For example, you could specify the OS version of iOS that must be installed before the app gets installed.|

## S
|||
|-|-|
|Selective wipe|A [selective wipe](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) removes only company data including mobile app management (MAM) data where applicable, settings, and email profiles from a device. Selective wipe leaves the user's personal data on the device.|
|Subscription|The agreement you enter that allows you to access an Intune tenant.|

## T
|||
|-|-|
|TeamViewer|A third-party application that works with Intune to provide [remote assistance capabilities](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) for Windows PCs managed with the Intune software client.|
|Tenant|A single instance of the Intune service you can access with a subscription.|
|Terms and conditions|A policy type you deploy to users that contains information users must [read and accept](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) before they can use the Company Portal to enroll and access their work.|

## V
|||
|-|-|
|Volume-purchased app|Some app stores give you the ability to purchase multiple licenses for an app that you want to run in your company. Intune helps you manage apps that you [purchased through such a program](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune) by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.|
|VPN profile|A policy that deploys [VPN settings](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune) to devices you manage, minimizing any setup required for end users.|

## W
|||
|-|-|
|Wi-Fi profile|A policy that deploys [wireless network settings](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune) to devices to let users connect to your company network without needing to know, or configure any settings.
