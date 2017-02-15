---
# required metadata

title: Intune custom settings for Windows Phone 8.1 devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about the settings you can use in a Windows Phone 8.1 custom profile."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Custom settings for Windows Phone 8.1 devices in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use the Microsoft Intune Windows Phone 8.1 **Custom** profile to deploy OMA-URI settings that can be used to control features on Windows Phone 8.1 devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy settings that are not configurable with other Intune policies.

## Custom policy settings for Windows Phone 8.1 devices

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) to get started.
2. On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.
3. On the **Add Row** blade, configure the following values for each setting:
	- **Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
	- **Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.
	- **OMA-URI** - Specify the OMA-URI you want to supply a setting for.
	- **Data type** - Select the data type in which you will specify this OMA-URI setting. Choose from **String**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.
	- **Value** - Enter the value you want to associate with the OMA-URI you entered.

4. Click **OK** once you are done, then continue to add more settings as required.
