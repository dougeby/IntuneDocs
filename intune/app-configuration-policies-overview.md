---
# required metadata

title: App configuration policies for Intune | Microsoft Docs 
titlesuffix: "Azure portal"
description: Learn about to use app configuration policies for Intune.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/27/2017
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

Use app configuration policies in Microsoft Intune to supply settings when users run an iOS or Android app. For example, an app might require users to specify:

- A custom port number.
- Language settings.
- Security settings.
- Branding settings such as a company logo.

If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app. The settings are then supplied automatically, and users need to take no action. 

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings are used whenever the app checks for them (typically, the first time it is run).

You have two options for how to use app configurations with Intune:
 - **Managed devices**  
   The device is managed by Intune as a MDM solution.
 - **Managed apps**  
   The app can be managed without device enrollment.

## Apps that support app configuration

Apps must have been written to support the use of app configurations. Consult your app vendor for more information.

You can use app configuration polices for apps that support it 

You can use the [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) to prepare line-of-business apps to be managed by Intune app protection policies, and app configuration policies, whether the device is enrolled with Intune or not. For example, you can use an app configuration policy to configure allowed and blocked URLs for the [Intune Managed Browser](app-configuration-managed-browser.md). Once an app is compatible with these policies, you can configure them using a policy.

When the assigned app is run on a device, it runs with the settings that you configured in the app configuration policy.
See the documentation for the app you are configuring for information about what happens if one or more app configuration policies conflict.

Additionally, you can use Graph API to accomplish these tasks. For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## Next steps

### Managed devices

 - Learn how to use app configuration with your iOS devices.  See [ Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).
 - Learn how to use app configuration with your Android devices.  See [Add app configuration policies for managed Android devices](app-configuration-policies-use-ios.md).

### Managed apps

 - Learn how to use app configuration with managed apps. See [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-overview.md).