---
# required metadata

title: Windows Team configuration policy settings
description: Use the Microsoft Intune **Windows 10 Team general configuration policy** to configure settings for enrolled Windows 10 Team devices such as the Microsoft Surface Hub.
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Windows Team configuration policy settings in Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Use the Microsoft Intune **Windows 10 Team general configuration policy** to configure settings for enrolled Windows 10 Team devices such as the Microsoft Surface Hub.


|                                  Setting name                                   |                                                                                                                                                                Details                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Allow screen to wake automatically when someone in the room</strong>   |                                                                                                                         Allows the device to wake automatically when its sensor detects someone in the room.                                                                                                                          |
|              <strong>Require PIN for wireless projection</strong>               |                                                                                                             Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.                                                                                                             |
|          <strong>Set a maintenance window for device updates</strong>           |                                                                                          Configures the window when updates can take place to the device. You can configure the start time of the window and the duration (from 1-5 hours).                                                                                           |
|               <strong>Enable Azure Operational Insights</strong>                |                  Azure Operational Insights , part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.<br /><br />To connect to Azure Operational insights, you must specify a <strong>Workspace ID</strong> and a <strong>Workspace Key</strong>.                   |
|              <strong>Enable Miracast wireless projection</strong>               |                                          Enable this option if you want to let the Windows 10 Team device use Miracast enabled devices to project.<br /><br />If you enable this option, from <strong>Choose Miracast channel</strong> select the Miracast channel used to project content.                                           |
| <strong>Choose the meeting information displayed on the welcome screen</strong> | If you enable this option, you can choose the information that will be displayed on the <strong>Meetings</strong> tile of the <strong>Welcome</strong> screen. You can:<br /><br />-   <strong>Show organizer and time only</strong><br />-   <strong>Show organizer, time and subject (subject hidden for private meetings)</strong> |
|                <strong>Lockscreen background image URL</strong>                 |                                           Enable this setting to display a custom background on the <strong>Welcome</strong> screen of Windows 10 Team devices from the URL you specify.<br /><br />The image must be in PNG format and the URL must begin with <strong>https://</strong>.                                            |

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

