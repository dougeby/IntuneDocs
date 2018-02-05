---
# required metadata

title: About Android for Work 
description: Intune manages Android for Work to provide additional management capabilities and privacy when people use their Android devices for work.
keywords:
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
#ms.reviewer: chrisbal
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Manage Android for Work devices with Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work is a set of Android device features and services that separate personal apps and data from a work profile containing work apps and data. Android for Work provides additional management capabilities and privacy when people use their Android devices for work. Intune helps you deploy apps and company resources to Android for Work devices to ensure work and personal information is separate. When successfully deployed, apps and the data they access remain exclusively within the Android for Work environment on the device.

## Supported devices

Android for Work management capabilities rely upon features that are part of newer Android operating system. Android for Work is currently supported on devices running Android 5.0 Lollipop and later that support a work profile. For devices that do not support Android for Work, conventional Android management remains available. Learn more about [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## Onboarding

Before enrolling Android for Work devices, you must complete some onboarding steps. These steps establish a connection between your Intune tenant and Google’s Play for Work service, which is an integral part of the Android for Work app distribution and management process. Learn more about [Enabling Android for Work enrollment](/intune-classic/deploy-use/set-up-android-for-work).

## Work profile management

When you manage an Android for Work device with Intune, you don’t manage the entire device. Management capabilities only affect the work profile that is created on the device during enrollment. Any apps deployed to the device with Intune get installed in the work profile. App icons in the work profile display an orange briefcase to differentiate work apps from personal apps on the device. All Android apps and data outside the Android for Work portion of the device remain personal and under the control of the end user. Users can install any app they choose to the personal side of the device, while administrators can manage and monitor apps and actions scoped to the work profile.

Intune supplies a range of built-in general settings that you can configure on Android for Work devices. Learn more about [Android for Work policy settings](android-for-work-policy-settings-in-microsoft-intune.md)

## App publishing and distribution

The Google Play for Work service is an integral part of Android for Work app distribution and management. All apps deployed to Android for Work devices in the work profile come from Play for Work service. To manage and deploy apps in the Play Store, you log in to the Google Play website with your company's administrator credentials for Google management. You can approve apps for Android for Work deployment to have them appear in devices' work profiles. These apps then sync to the Intune console where they can then be deployed and managed using Intune. Line of business (LOB) apps developed by your organization must be published to Play for Work using Google’s Android app publishing console. Line-of-business apps must be configured in the Android app publishing console to restrict access to your organization.

Apps can be installed without user interaction and without requiring that the user allow **Installation from Unknown Sources**. To browse and install optional or available apps, the user can browse the Play for Work store on their device. Learn more about [Deploying apps for Android for Work](/intune-classic/deploy-use/android-for-work-apps).

## App configuration

Android for Work provides infrastructure for deploying app configuration values to apps that support them. By specifying configuration values for work apps, you ensure they are properly set when users launch the app for the first time. Support for app configuration requires that app developers create their Android apps specifically to support managed configuration values. If they do, then you can use Intune to specify and apply these configuration settings. Learn more about [Android for Work app configuration settings](afw-app-configuration-policy.md).

## Email configuration

Android for Work doesn’t provide a default email app or native email profile object like that which is provided by iOS. Instead, email configurations can be set by applying app configuration settings to email apps that support them. Gmail and Nine Work are two Exchange ActiveSync (EAS) client apps in the Play Store that support configuration with Android for Work app configuration.

Intune provides configuration templates for Gmail and Nine Work apps when managed as work apps. Other email apps that supports app configuration profiles can be configured with mobile app configuration policies.

If you are using Exchange ActiveSync conditional access for an Android for Work devices, you must use either the Gmail or Nine Work email app. The Microsoft Outlook for Android app, or any other email app that uses modern authentication via ADAL, is also supported. Learn more about [Email profiles for company email](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## App protection policies

App protection policies applied are fully supported in the work profile and in the personal profile. You can publish line-of-business apps in the Android app publishing console at https://play.google.com/apps/publish. This console includes an option to make apps private to your organization. Learn more about [Android for Work compliance policy settings](afw-compliance-policy-settings-in-microsoft-intune.md). For general information about app protectino policies, see [app policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## VPN profiles

VPN support is similar to Android VPN profiles. The same VPN providers and basic configuration options are available for Android for Work management with two differences:

-  **Work profile-scoped VPN** – VPN connections are limited to just the apps deployed to the work profile. Only Android for Work-managed apps can use the VPN connection. Personal apps on the device cannot use a managed VPN connection.

-  **App-specific VPN** – If a VPN provider supports configuration for app-specific VPN and provides the capability to configure per-app VPN via the Android for Work app configuration profile, then a app-specific VPN can be configured in Intune. Check with the VPN provider to see if they support this capability. Learn more about [VPN connection profiles](vpn-connections-in-microsoft-intune.md).

## Certificate profiles

The same certificate profile configuration options that are available to Android management are available on Android for Work devices. Android for Work provides enhanced certificate management APIs. Enhanced certificate management provides the following functionality:

- Ensures that cert deployment is silent and seamless for the user.
-  Ensures that deployed certs are completely removed when a device is retired from Intune and the work profile is removed.
-  Provides improved messaging that informs users that the certificate was deployed and configured by their IT department via their management service.

Learn more about [Certificate profiles](secure-resource-access-with-certificate-profiles.md).

## Wi-Fi profiles

Wi-Fi profiles managed by Android for Work are removed when the device is retired from Intune and the work profile is deleted. Learn more about [Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md).

## Next steps
[Enabling Android for Work enrollment](/intune-classic/deploy-use/set-up-android-for-work)

[Deploying apps for Android for Work](/intune-classic/deploy-use/android-for-work-apps)
