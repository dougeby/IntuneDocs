---
title: Windows Phone custom policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f64674ff-f2a6-471c-82a5-bcff23c7514d
author: robstackmsft
---
# Windows Phone custom policy settings in Microsoft Intune
Use the Microsoft Intune **Windows Phone custom configuration policy** to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on **Windows Phone 8.1 devices**. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Windows Phone settings that are not configurable with an Intune general configuration policy. For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

For help creating OMA-URI settings for Windows Phone devices, see [Windows Phone 8.1 MDM protocol documentation](http://technet.microsoft.com/library/dn499787.aspx).

## General settings

|Setting name|Details|
|----------------|--------------------|
|**Name**|Enter a unique name for the policy to help you identify it in the Intune console.|
|**Description**|Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.|

## OMA-URI settings

In the **OMA-URI Settings** section, click **Add** to add a setting. You can also edit or delete an existing setting.

In the **Add or Edit OMA-URI Setting** dialog box, specify the following information:

|Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from:<br /><br />-   **String**<br />-   **String (XML)**<br />-   **Date and time**<br />-   **Integer**<br />-   **Floating point**<br />-   **Boolean**|
    |**OMA-URI (Case Sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|

### See Also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

