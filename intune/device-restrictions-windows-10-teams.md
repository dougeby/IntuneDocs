---
# required metadata

title: Intune device restrictions for Windows 10 Team
titlesuffix: "Azure portal"
description: Learn about the device restrictions available for Windows 10 Team devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows 10 Team device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## Apps and experience

- **Wake screen when someone in room** - Allows the device to wake automatically when its sensor detects someone in the room.
- **Meeting information displayed on welcome screen** - Enable this option to choose the information that is displayed on the Meetings tile of the Welcome screen. You can:
	- **Show organizer and time only**
	- **Show organizer, time, and subject (subject hidden for private meetings)**
- **Welcome screen background image URL** - Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.<br>The image must be in PNG format and the URL must begin with **https://**.

## Azure operational insights

- **Azure Operational Insights** - Azure Operational Insights, part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.
To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.

## Maintenance

- **Maintenance window for updates** - Configures the window when updates can take place to the device. You can configure the **Start time** of the window and the **Duration in hours** (from 1-5 hours).

## Wireless projection

- **PIN for wireless projection** - Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.
- **Miracast wireless projection** - If you want to let the Windows 10 Team device use Miracast enabled devices to project, select this option.
- **Miracast wireless projection channel** - Choose the Miracast channel that will be used to establish the connection.


## Next steps

Use the information in [How to configure device restriction settings](device-restrictions-configure.md) to save, and assign the profile to users and devices.
