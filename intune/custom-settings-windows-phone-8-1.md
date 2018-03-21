---
# required metadata

title: Microsoft Intune custom settings for devices running Windows Phone 8.1 
titleSuffix:
description: Learn about the settings you can use in a Windows Phone 8.1 custom profile.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Microsoft Intune custom device settings for devices running Windows Phone 8.1

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the Microsoft Intune Windows Phone 8.1 **Custom** profile to assign OMA-URI settings that can be used to control features on Windows Phone 8.1 devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to assign settings that are not configurable with other Intune policies.

## Custom policy settings for Windows Phone 8.1 devices

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.
2. On the **Custom OMA-URI Settings** pane, choose **Add** to add one or more OMA-URI settings.
3. On the **Add Row** pane, configure the following values for each setting:
	- **Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
	- **Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.
	- **OMA-URI** - Specify the OMA-URI you want to supply a setting for.
	- **Data type** - Select the data type in which to specify this OMA-URI setting. Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, **Boolean**, or **Base64**.
	- **Value** - Enter the value or file you want to associate with the OMA-URI you entered.

4. Click **OK** once you are done, then continue to add more settings as required.
