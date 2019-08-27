---
# required metadata

title: App configuration policies for Microsoft Intune
titleSuffix: 
description: Learn how to use app configuration policies on an iOS or Android device in Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708

# optional metadata 

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# App configuration policies for Microsoft Intune

Use app configuration policies in Microsoft Intune to provide configuration settings for an iOS or Android app. These configuration settings allow an app to be customized by using an industry standard approach to app configuration and management. The configuration policy settings are used when the app checks for these settings, typically the first time the app is run. App configuration policies can help provide consistency across an enterprise and reduce helpdesk calls from end users trying to configure settings on their own.

The available configuration parameters are ultimately decided by the app developers of what can and cannot be configured. Documentation from the application vendor should be reviewed to see if an app supports configuration and what configurations are available. For some applications, Intune will populate what configurations are available. In the Managed Google Play Store, apps that support configuration will be marked as such:

![Screenshot of a configured app](./media/app-configuration-policy-overview/configured-app.png)

You can assign an app configuration policy to a group of users and devices by using a combination of include and exclude assignments. Once you add an app configuration policy, you can set the assignments for the app configuration policy. When you set the assignments for the policy, you can choose to include and exclude the groups of users for which the policy applies. When you choose to include one or more groups, you can choose to select specific groups to include or select built-in groups. Built-in groups include **All Users**, **All Devices**, and **All Users + All Devices**.

An app configuration setting, for example, might require you to specify any of the following details:

- A custom port number
- Language settings
- Security settings
- Branding settings such as a company logo

If users were to enter these settings instead, they could do this incorrectly, which could increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate app setup up problems by letting you assign configation settings to a policy that is assigned to users before they run the app. The settings are then supplied automatically, and users need to take no action.

The configuration settings are used whenever the app checks for them. Typically, an app checks for configuration settings the first time the app is run by the user.

You have two options for how to use app configurations with Intune:
- **Managed devices** - The device is managed by Intune as the mobile device management (MDM) provider.
- **Managed apps** - An app is managed without device enrollment. These apps must be targeted with an Intune App Protection policy.  Apps that support Intune App Protection policies have the Intune SDK-enabled.

> [!NOTE]
> As the Microsoft Intune admin, you can control which user accounts are added to Microsoft Office applications on managed devices. You can limit access to only allowed organization user accounts and block personal accounts on enrolled devices. The supporting applications process the app configuration and remove and block unapproved accounts.

You will only see apps from [Managed Google Play store](https://play.google.com/work), and not the standard [Google Play store](https://play.google.com/store/apps), when using Managed Devices as the Enrollment Type. Managed Google Play Store, which you may also know as Android for Work (AfW) and Android Enterprise, are the apps in the Work Profile that contain the app versions that support app configuration.

## Apps that support app configuration

### Managed devices
You can use app configuration polices for apps that support it. To support app configuration in Intune, apps must have been written to support the use of app configurations as defined by the [Appconfig Community](https://www.appconfig.org/members). Consult your app vendor for details.

### Managed apps
You can prepare your line-of-business apps by either incorporating the Intune App SDK into the app, or wrapping the app after it is developed. The Intune App SDK, available for both iOS and Android, enables your app for Intune app protection configuration policies. It strives to minimize the amount of code changes required from the app developer. For more information, see the [Intune App SDK overview](app-sdk.md).

Selecting **Managed apps** as the **Device Enrollment Type** specifically refers to apps protected by Intune App Protection policies on a device that is not enrolled in device management, whereas **Managed devices** applies to apps deployed through the MDM channel and thus are managed by Intune. Select the appropriate choice based on these descriptions. 

![Device enrollment type](./media/app-configuration-policy-overview/device-enrollment-type.png)

For multi-identity apps like Outlook, user preferences may be considered. Focused Inbox, for example, will respect the user setting and not change the configuration. Other parameters do let you control if a user may or may not change the setting.

## Validate the applied app configuration policy

You can validate the app configuration policy using the following three methods:

   1. Visibly on the device. Is the targeted app exhibiting the behavior applied in the App Configuration policy?
   2. Via Diagnostic Logs (see the Diagnostic Logs section below).
   3. In the Intune Portal. The **Monitor** section of a policy can provide the relevant status:

      ![First screenshot of device install status](./media/app-configuration-policy-overview/device-install-status-1.png)

      ![Second screenshot of device install status](./media/app-configuration-policy-overview/device-install-status-2.png)

      Additionally, under **Intune** -> **Devices** -> **All Devices** on the left side of the screen, the **App Configuration** option will display all the assigned policies and their state:

      ![Screenshot of app configuration](./media/app-configuration-policy-overview/app-configuration.png)

## Graph API support for app configuration

You can use Graph API to accomplish app configuration tasks. For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## Troubleshooting

### Using logs to show a configuration parameter
When the logs show a configuration parameter that is confirmed to be applying but doesn't seem to work, there may be an issue with the configuration implementation by the app developer. Reaching out to that app developer first, or checking their knowledge base, may save you a support call with Microsoft. If it is an issue with the how the configuration is being handled within an app, it would have to be addressed in a future updated version of that app.

## Next steps

### Managed devices

- Learn how to use app configuration with your iOS devices.  See [Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).
- Learn how to use app configuration with your Android devices.  See [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md).

### Managed apps

- Learn how to use app configuration with managed apps. See [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).
