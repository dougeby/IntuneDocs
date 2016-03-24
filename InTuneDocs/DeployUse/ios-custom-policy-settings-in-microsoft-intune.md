---
title: iOS custom policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 04e60d5a-3da6-4943-b6ff-e6a331bcbcfa
author: robstackmsft
---
# iOS custom policy settings in Microsoft Intune
Use the Microsoft Intune **iOS custom policy** to deploy settings that you created using the [Apple Configurator tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) to iOS devices. This tool lets you create many settings that control the operation of these devices and export them to a configuration profile. You can then import this configuration profile into an Intune iOS custom policy and deploy the settings to users and devices in your organization.

This capability is intended to allow you to deploy iOS settings that are not configurable with Intune general configuration policies policies. For information about the settings you can configure with these policies, see [iOS configuration policy settings in Microsoft Intune](iOS-configuration-policy-settings-in-Microsoft-Intune.md).

## Prerequisites
Before you start, you must have installed the Apple Configurator and created a configuration file containing the settings you want to deploy to users or devices. You can download and learn about the Apple Configurator from [the Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)

> [!NOTE]
> Intune does not report the compliance of individual settings in an iOS custom policy. However, the overall compliance of the policy is reported.

## General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the iOS custom policy to help you identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description that gives an overview of the iOS custom policy and other relevant information that helps you to locate it.|

##Custom settings

|Setting name|Details|
    |----------------|--------------------|
|**Custom configuration profile name (displayed to users)**|Provide a name for the policy as it will be displayed on the device, and in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy reports.|
|**Configuration profile file**|Click **Import**, then browse to the configuration profile that you created using the Apple Configurator. **Note:** Ensure that the settings you export from the Apple Configurator tool are compatible with the version of iOS on the devices to which you deploy the iOS custom policy. For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) web site.|
    |**Configuration profile details**|Displays the xml code for the configuration profile that you imported.|


### See Also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

