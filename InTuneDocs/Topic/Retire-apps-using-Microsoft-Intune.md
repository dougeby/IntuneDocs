---
title: Retire apps using Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
author: robstackmsft
---
# Retire apps using Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] can help you retire apps. Use the information in this topic to understand how you can uninstall an ap when it is no longer required.

## How to retire apps
When you deploy and manage apps with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], the process to uninstall the app is the same for both mobile devices and computers. The app must support being uninstalled for this procedure to succeed.

#### To uninstall an app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Apps** &gt; **Apps**.

2.  Select the app you want to uninstall (which you have previously deployed), and then click **Manage Deployment**.

3.  On the **Deployment Action** page, select **Uninstall** from the **Approval** column.

When the device or computer next checks for apps, the app will be uninstalled.

## See Also
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md)
[Update apps using Microsoft Intune](../Topic/Update-apps-using-Microsoft-Intune.md)

