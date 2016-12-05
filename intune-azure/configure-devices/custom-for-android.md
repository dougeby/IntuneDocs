---
# required metadata

title: Intune custom settings for Android devices | Microsoft Docs
description: Learn the settings you can use in an Android custom profile.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Custom for Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use the Microsoft Intune Android **Custom** profile to deploy OMA-URI settings that can be used to control features on Android devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Android settings that are not configurable with Intune policies.

## Custom profile settings for Android devices

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) to get started.
2. On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.
3. On the **Edit Row** blade, configure the following values for each setting:
	- **Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
	- **Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.
	- **Data type** - Select the data type in which you will specify this OMA-URI setting. Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.
	- **OMA-URI** - Specify the OMA-URI you want to supply a setting for.
	- **Value** - Enter the value you want to associate with the OMA-URI you entered.
4. Click **OK** once you are done, then continue to add more settings as required.


