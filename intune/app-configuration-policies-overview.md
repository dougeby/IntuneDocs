---
# required metadata

title: App configuration policies for Intune
titlesuffix: Microsoft Intune
description: Learn how to use app configuration policies on an iOS or Android device in Intune.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708

# optional metadata 

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# App configuration policies for Intune

Supply settings when users run an iOS or Android app with app configuration policies in Microsoft Intune. For example, an app might require users to specify:

- A custom port number.
- Language settings.
- Security settings.
- Branding settings such as a company logo.

If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app. The settings are then supplied automatically, and users need to take no action.

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings are used whenever the app checks for them (typically, the first time it is run).

You have two options for how to use app configurations with Intune:
 - **Managed devices**  
   The device is managed by Intune as the mobile device management (MDM) provider.
 - **Managed apps**  
   An app is managed without device enrollment.

## Apps that support app configuration

You can use app configuration polices for apps that support it. To support app configuration in Intune, apps must have been written to support the use of app configurations. Consult your app vendor for details.

You can prepare your line-of-business apps by either incorporating the Intune App SDK into the app, or wrapping the app after it is developed. The Intune App SDK, available for both iOS and Android, enables your app for Intune app protection policies. It strives to minimize the amount of code changes required from the app developer. For more information, see the [Intune App SDK overview](app-sdk.md).

## Graph API support for app configuration

Additionally, you can use Graph API to accomplish app configuration tasks. For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## Next steps

### Managed devices

 - Learn how to use app configuration with your iOS devices.  See [ Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).
 - Learn how to use app configuration with your Android devices.  See [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md).

### Managed apps

 - Learn how to use app configuration with managed apps. See [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).