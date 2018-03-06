---
# required metadata

title: Microsoft Intune custom settings for devices running iOS 
titleSuffix: "Azure portal"
description: Learn the settings you can use in an iOS custom profile.
keywords:
author: vhorne
ms.author: victorh
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

# Microsoft Intune custom device settings for devices running iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the Microsoft Intune iOS custom profile to assign settings that you created by using the [Apple Configurator tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) to iOS devices. This tool lets you create many settings that control the operation of these devices and export them to a configuration profile. You can then import this configuration profile into an Intune iOS custom profile and assign the settings to users and devices in your organization.

This capability allows you to assign iOS settings that are not configurable with other Intune profile types.


1. Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.
2. On the **Custom Configuration Profile** pane, configure each of the following settings:

- **Custom configuration profile name** - Provide a name for the policy as displayed on the device, and in Intune status.
- **Configuration profile file** - Browse to the configuration profile that you created by using the Apple Configurator.
Ensure that the settings you export from the Apple Configurator tool are compatible with the version of iOS on the devices to which you assign the iOS custom policy. For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.

The file you imported is displayed in the **File contents** area of the pane.
