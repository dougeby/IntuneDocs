---
# required metadata

title: How to assign apps to groups 
titlesuffix: "Azure portal"
description: Once you've added an app to Intune, you'll want to assign it to groups of users or devices."
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to assign apps to groups with Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Once you've added an app to Intune, you can assign it to users and devices.

Apps can be assigned to devices whether or not they are managed by Intune. Use the following table to help you understand the various options for assigning apps to users and devices:

||||
|-|-|-|-|
|&nbsp;|Devices enrolled with Intune|Devices not enrolled with Intune|
|Assign to users|Yes|Yes|
|Assign to devices|Yes|No|
|Assign wrapped apps, or apps incorporating the Intune SDK (for app protection policies)|Yes|Yes|
|Assign apps as Available|Yes|Yes|
|Assign apps as Required|Yes|No|
|Uninstall apps|Yes|No|
|End users install available apps from Company Portal app|Yes|No|
|End users install available apps from web-based Company Portal|Yes|Yes|

> [!NOTE]
> Currently, you can assign iOS and Android apps (both line of business and store-purchased) to devices that are not enrolled with Intune.

## How to assign an app

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Mobile apps**.
1. In the **Mobile Apps** workload, choose **Manage** > **Apps**.
2. On the list of apps blade, click the app you want to assign.
3. On the <*app name*> - **Overview** blade, choose **Manage** > **Assignments**.
4. Choose **Add Group** then, on the **Add group** blade, choose the Azure AD groups to include or exclude from assigning the app.
5. For each app you choose, choose an **assignment type** for the app from:
	- **Available for enrolled devices** - Users install the app from the Company Portal app or website.
	- **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune.
	- **Required** - The app is installed on devices in the selected groups.
	- **Uninstall** - The app is uninstalled from devices in the selected groups.
6. **For iOS apps only** - If you have created an iOS VPN profile that contains per-app VPN settings, you can select it under **VPN**. When the app is run, the VPN connection is opened. For more information, see [VPN settings for iOS devices](vpn-settings-ios.md).
6. Once you are done, choose **OK** and then choose **Save**.

The app is now assigned to the groups you selected.

## How conflicts between app intents are resolved

Sometimes, the same app is assigned to multiple groups, but with different intents. In these cases, use this table to understand the resulting intent.

||||
|-|-|-|
|Group 1 intent|Group 2 intent|Resulting intent|
|User Required|User Available|Required and Available|
|User Required|User Not Available|Required|
|User Required|User Uninstall|Required|
|User Available|User Not Available|Not Available|
|User Available|User Uninstall|Uninstall|
|User Not Available|User Uninstall|Uninstall
|User Required|Device Required|Both exists, Gateway treats required 
|User Required|Device Uninstall|Both exists, Gateway resolves required 
|User Available|Device Required|Both exists, Gateway resolves required (Required and Available)
|User Available|Device Uninstall|Both exists, Gateway resolves Available.<br>App shows up in Company Portal.<br>In case if the app is already installed(as required app with previous intent) then the app gets uninstalled.<br>But if the user clicks install from the company portal then the app gets installed and uninstall intent is not honored.|
|User Not Available|Device Required|Required|
|User Not Available|Device Uninstall|Uninstall|
|User Uninstall|Device Required|Both exists, Gateway resolves Required|
|User Uninstall|Device Uninstall|Both exist, Gateway resolves Uninstall|
|Device Required|Device Uninstall|Required|
|User Required And Available|User Available|Required and Available|
|User Required And Available|User Uninstall|Required and Available|
|User Required And Available|User Not Available|Required and Available|
|User Required And Available|Device Required|Both exists Required and Available
|User Required And Available|Device Not Available|Required and Available|
|User Required And Available|Device Uninstall|Both exists, gateway resolves required. Required + Available
|User Not Available|Device Not Available|Not Available|
|User Available|Device Not Available|Available|
|User Required|Device Not Available|Required|
|User Available Without enrollment|User Required and Available|Required and Available
|User Available without enrollment|User Required|Required
|User Available without enrollment|User Not available|Not Available
|User Available without enrollment|User Available|Available|
|User Available without enrollment|Device Required|Required and Available without enrollment|
|User Available without enrollment|Device Not Available|Available without enrollment|
|User Available without enrollment|Device Uninstall|Uninstall and Available without enrollment.<br>If the user didn’t install the app from the company portal, then the uninstall is honored.<br>If the user installs the app from the company portal, then the install is prioritized over the uninstall.|

>[!NOTE]
>For managed iOS store apps only, when you add these to Intune and assign them as Required, they are automatically created with both Required, and Available intents.

## Next steps

See [How to monitor apps](apps-monitor.md) for information to help you monitor app assignments.
