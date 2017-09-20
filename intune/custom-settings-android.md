---
# required metadata

title: Intune custom settings for Android devicestitleSuffix: "Azure portal"
description: Learn the settings you can use in an Android custom profile."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/18/2017
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
ms.custom: intune-azure

---

# Custom settings for Android devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the Microsoft Intune Android **Custom** profile to assign OMA-URI settings that can be used to control features on Android devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to assign the following Android settings that are not configurable with Intune policies:

- [Use a Microsoft Intune custom device profile to create a Wi-Fi profile with a pre-shared key](/intune/wi-fi-profile-shared-key)
- [Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices](/intune/android-pulse-secure-per-app-vpn)
- [Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Only the settings listed above can currently be configured by this profile type. Android devices do not expose a complete list of OMA-URI settings you can configure. If you want to see further settings added, please request these on the [Intune Uservoice site](https://microsoftintune.uservoice.com/forums/291681-ideas).

## Custom profile settings for Android devices

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.
2. On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.
3. On the **Edit Row** blade, configure the following values for each setting:
	- **Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
	- **Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.
	- **Data type** - Select the data type in which you will specify this OMA-URI setting. Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.
	- **OMA-URI** - Specify the OMA-URI you want to supply a setting for.
	- **Value** - Enter the value you want to associate with the OMA-URI you entered.
4. Click **OK** once you are done, then continue to add more settings as required.

## Next steps

When you complete the settings, the profile will be created and appears on the profiles list blade. If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).




