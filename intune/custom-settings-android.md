---
# required metadata

title: Add custom settings for Android devices in Microsoft Intune - Azure | Microsoft Docs
description: Add or create a custom profile for Android devices to create a WiFi profile with a pre-shared key, create a per-app VPN profile, or allow/block apps for Samsung Knox Standard devices in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
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

# Custom settings for Android devices - Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Custom** profiles use Open Mobile Alliance Uniform Resource Identifier (OMA-URI) settings to configure different features on Android devices. These settings are typically used by mobile device manufacturers to control features on the device.

Using a custom profile, you can configure and assign the following Android settings: These settings aren't built in to the Intune policies:

- [Create a Wi-Fi profile with a pre-shared key](/intune/wi-fi-profile-shared-key)
- [Create a per-app VPN profile](/intune/android-pulse-secure-per-app-vpn)
- [Allow and block apps for Samsung Knox Standard devices](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Only the settings listed can be configured by this profile type. Android devices don't expose a complete list of OMA-URI settings you can configure. If you'd like to see more settings, then vote for more settings at the [Intune Uservoice site](https://microsoftintune.uservoice.com/forums/291681-ideas).

## Custom profile settings for Android devices

1. Sign in to the [Azure portal](https://portal.azure.com). 
2. Select **All Services**, filter on **Intune**, and select **Microsoft Intune**.
3. Create a custom profile using the Android platform. [Configure custom device settings in Microsoft Intune](custom-settings-configure.md) lists the steps.
4. In **Custom OMA-URI Settings**, select **Add**, and then select **Add Row**.
5. Enter the following properties:

  - **Name** - Enter a unique name for the OMA-URI setting so you can easily find it.
  - **Description** - Enter a description that gives an overview of the setting, and any other important details.
  - **Data type** - Enter the data type you use for this OMA-URI setting. Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.
  - **OMA-URI** - Enter the OMA-URI you want.
  - **Value** - Enter the value you want to associate with the OMA-URI you entered.

6. Select **OK** to save your changes. Continue to add more settings as needed.

## Next steps

When you complete the settings, the profile is created, and appears in the list. To assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).