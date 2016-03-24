---
title: Windows 10 custom policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5756b025-6fe9-418d-a1c4-cae576d31b79
author: robstackmsft
---
# Windows 10 custom policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] **custom configuration policy** for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on Windows 10 and Windows 10 Mobile devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Windows 10 settings that are not configurable with an [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] policy. For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

For a list of OMA-URI settings that you can configure on enrolled Windows 10 devices, see [Custom URI settings for Windows 10 devices](Custom-URI-settings-for-Windows-10-devices.md).

## General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the policy to help you identify it in the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] console.|
    |**Description**|Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.|

## OMA-URI settings

|Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from:<br /><br />-   **String**<br />-   **String (XML)**<br />-   **Date and time**<br />-   **Integer**<br />-   **Floating point**<br />-   **Boolean**|
    |**OMA-URI (case sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|



### See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md)

