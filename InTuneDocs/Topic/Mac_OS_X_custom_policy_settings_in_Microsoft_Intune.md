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
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**Mac OS X custom configuration policy** to deploy settings that you created using the [Apple Configurator tool](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to Mac OS X devices. This tool lets you create many settings that control the operation of these devices and export them to a configuration profile. You can then import this configuration profile into a [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Mac OS X custom policy and deploy the settings to users and devices in your organization.

This capability is intended to allow you to deploy Mac OS X settings that are not configurable with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Mac OS X general configuration policy. For information about the settings you can configure with these policies, see [Mac OS X configuration policy settings in Microsoft Intune](../Topic/Mac_OS_X_configuration_policy_settings_in_Microsoft_Intune.md).

## Prerequisites
Before you start, you must have installed the Apple Configurator and created a configuration file containing the settings you want to deploy to users or devices. You can download and learn about the Apple Configurator from [the Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

> [!NOTE]
> [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not report the compliance of individual settings in a Mac OS X custom policy. However, the overall compliance of the policy is reported.

## How to create a Mac OS X custom policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Configure a policy of the type **Mac OS X** &gt; **Custom Configuration**.

    For help creating and deploying policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

    You can only create and deploy a custom Mac OS X  custom policy. Recommended settings are not available.

3.  Use the following table to help you configure the policy settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the Mac OS X custom policy to help you identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description that gives an overview of the Mac OS X custom policy and other relevant information that helps you to locate it.|
    |**Custom configuration profile name (displayed to users)**|Provide a name for the policy as it will be displayed on the device, and in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy reports.|
    |**Configuration profile file**|Click **Import**, then browse to the configuration profile that you created using the Apple Configurator. **Tip:** See [How to create a configuration profile file](#BKMK_Prof) in this topic for help creating the configuration profile.|
    |**Configuration profile details**|Displays the xml code for the configuration profile that you imported.|

4.  When you are finished, click **Save Policy**.

5.  The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## <a name="BKMK_Prof"></a>How to create a configuration profile file
You can create the configuration profile file used by the custom policy in two ways:

-   Export the file (with the extension **.mobileconfig**) from the Apple Configurator tool.

-   Author the file yourself using the appropriate schema from the [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).

## Deploy a Mac OS X custom policy

-   Deploy the Mac OS X custom policy to one or more groups of users or devices in your organization.

For help deploying policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!IMPORTANT]
> When a Mac OS X device is in Sleep mode, policies and profiles cannot be delivered or inventoried. As a result, the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console might temporarily display the status **Policy settings in error** until the next time the device wakes from Sleep mode.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md)

