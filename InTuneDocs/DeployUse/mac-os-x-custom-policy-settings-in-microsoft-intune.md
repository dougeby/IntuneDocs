---
title: Mac OS X custom policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 70459e56-17d8-4d3f-803d-22feefa7a5b6
author: robstackmsft
---
# Mac OS X custom policy settings in Microsoft Intune
Use the Microsoft Intune **Mac OS X custom configuration policy** to deploy settings that you created using the [Apple Configurator tool](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to Mac OS X devices. This tool lets you create many settings that control the operation of these devices and export them to a configuration profile. You can then import this configuration profile into an Intune Mac OS X custom policy and deploy the settings to users and devices in your organization.

This capability is intended to allow you to deploy Mac OS X settings that are not configurable with the Intune Mac OS X general configuration policy. For information about the settings you can configure with these policies, see [Mac OS X configuration policy settings in Microsoft Intune](mac-os-x-configuration-policy-settings-in-microsoft-intune.md).

## Prerequisites
Before you start, you must have installed the Apple Configurator and created a configuration file containing the settings you want to deploy to users or devices. You can download and learn about the Apple Configurator from [the Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

> [!NOTE]
> Intune does not report the compliance of individual settings in a Mac OS X custom policy. However, the overall compliance of the policy is reported.

## General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the Mac OS X custom policy to help you identify it in the Intune console.|
    |**Description**|Provide a description that gives an overview of the Mac OS X custom policy and other relevant information that helps you to locate it.|


## Custom settings

|Setting name|Details|
    |----------------|--------------------|
    |**Custom configuration profile name (displayed to users)**|Provide a name for the policy as it will be displayed on the device, and in Intune policy reports.|
    |**Configuration profile file**|Click **Import**, then browse to the configuration profile that you created using the Apple Configurator. **Tip:** See [How to create a configuration profile file](#BKMK_Prof) in this topic for help creating the configuration profile.|
    |**Configuration profile details**|Displays the xml code for the configuration profile that you imported.|



## How to create a configuration profile file
You can create the configuration profile file used by the custom policy in two ways:

-   Export the file (with the extension **.mobileconfig**) from the Apple Configurator tool.

-   Author the file yourself using the appropriate schema from the [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


> [!IMPORTANT]
> When a Mac OS X device is in Sleep mode, policies and profiles cannot be delivered or inventoried. As a result, the Intune console might temporarily display the status **Policy settings in error** until the next time the device wakes from Sleep mode.

### See Also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

