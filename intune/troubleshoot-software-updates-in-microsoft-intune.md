---
# required metadata

title: Troubleshoot software updates in Microsoft Intune - Azure | Microsoft Docs
description: Solve software update problems in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/28/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: 

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic
ms.collection: M365-identity-device-management
---

# Troubleshoot software updates in Microsoft Intune

Help solve software update problems in Microsoft Intune. If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).

To see a list of the error codes and descriptions, go to [Software update agent error codes in Microsoft Intune](software-update-agent-error-codes.md).

## Windows 7-based computers with lots of superseded updates stop reporting to the Intune console

You may encounter a situation where Microsoft Intune clients experience one or more of the following symptoms:

- They suddenly stop reporting to the Microsoft admin console.  
- They experience high CPU utilization.
- Applications install slowly when they’re installed through the Intune portal.
- The Microsoft Intune Center triggers the following error: *An error occurred while updating your computer. Error found: Code 0x800705b4*.
- The status field under Intune Admin Console > Groups > All Devices displays: *One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date*.

This problem may occur if superseded updates (updates that have been replaced by another update) have not been declined for an extended period. During certain processes, such as installing an application, Windows checks all superseded updates in sequence so that the updates and their successors can be correctly mapped. If the list of superseded updates grows too large, this checking task may cause high CPU utilization because of the processing load and time required. This issue primarily affect clients that are running Windows 7 because of the large number of superseded updates that are available for Windows 7. Windows 8 and later operating systems do not have as many available superseded updates and therefore are not as susceptible to this issue.

**Resolution**

1. In the [Azure portal](https://portal.azure.com), open **Microsoft Intune**. 
2. Select **Software Updates**.
3. Decline all superseded updates that may apply to Windows 7 or to applications (for example, Microsoft Office) that were installed on the affected clients.
4. Restart the affected clients.

Additionally, if you're running Windows 7, make sure that you have the following update installed:[3050265 Windows Update Client for Windows 7: June 2015](https://support.microsoft.com/kb/3050265).

## Next steps

If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).