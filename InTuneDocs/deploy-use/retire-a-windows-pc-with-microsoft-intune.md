---
# required metadata

title: Retire a Windows PC | Microsoft Docs
description: How to retire an Intune-managed Windows PC.
keywords:
author: staciebarkerms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Retire a Windows PC
Use the following steps to retire PCs that are managed by Intune.

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer you want to retire).

2.  Select the devices you want to retire, and then choose **Retire/Wipe**.

To re-enroll a computer into Intune, reinstall the software client on the PC using guidance in [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

If a computer cannot connect to Intune, a message is displayed in the **Dashboard** workspace.

When you retire a computer:

-   It is removed from the Intune management and inventory, and the license associated with the computer is made available for re-use. Retire/Wipe removes the Intune software client but does not remove apps or data from the computer. This retirement does not perform a full wipe on the computer.

-   Its status no longer displays in the Intune console.

-   Intune removes the software client from the computer. If the computer is not connected to the Intune service, the software client will be removed next time it connects.

-   Microsoft Intune Endpoint Protection is removed from the computer. If the computer has another endpoint application installed and it is disabled, that application can be re-enabled after Microsoft Intune Endpoint Protection is removed to ensure that your computers are protected.

-   Any policies are removed from the computer and the values that were set by the policy will be changed.

-   The computer no longer receives software updates or malware definition updates from the Intune service.

-   Depending on how they are configured, retired computers can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.

    > [!IMPORTANT]
    > If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.

    If the client fails to uninstall, read [Troubleshoot Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) for more help.

### See also

[Common Windows PC management tasks with the Intune software client](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)