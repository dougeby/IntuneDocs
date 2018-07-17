---
title: Troubleshoot app installation issues
titlesuffix: Microsoft Intune
description: Use the Microsoft Intune troubleshooting pane to help you troubleshoot app installation issues.
keywords:
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/17/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Troubleshoot app installation issues

On Microsoft Intune MDM-managed devices, sometimes app installations can fail. When these app installs fail, it can be challenging to understand the failure reason or troubleshoot the issue. Microsoft Intune provides app installation failure details that allow help desk operators and Intune administrators to view app information to address user help requests. The troubleshooting pane within Intune provides failure details, including details about managed apps on a user's device. Details about the end-to-end lifecycle of an app are provided under each individual device in the **Managed Apps** pane. You can view installation issues, as well as details about when the app was created, modified, targeted, and delivered to a device. This information can be used help administrators and help desk operators troubleshoot problems. 

> [!Note]  
> The same app could be assigned to multiple groups but with different intended actions (or intents) for the app. For instance, a resolved intent for an app will show **Excluded** if the app is excluded for a user during app assignment. For more information, see [How conflicts between app intents are resolved](apps-deploy.md#how-conflicts-between-app-intents-are-resolved). 

## To review app troubleshooting details

Intune provides app troubleshooting details based on the apps installed on a specific user's device.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Troubleshoot**.
4. Click **Select user** to select a user to troubleshoot. The **Select users** pane will be displayed.
5. Select a user by typing the name or email address. Click **Select** at the bottom of the pane. The troubleshooting information for the user is displayed in the **Troubleshoot** pane. 
6. Select the device that you want to troubleshoot from the **Devices** list.
	![The Intune Troubleshooting pane.](media/troubleshoot-app-install-01.png)
7. Select **Managed Apps** from selected device pane. A list of managed apps is displayed.
	![Details of a specific device managed by Intune.](media/troubleshoot-app-install-02.png)

    > [!Note]  
    > Currently, Intune does not filter out apps based on the OS platform.

8. Select an app from the list where **Installation Status** indicates a failure.
	![A selected app that shows installation failure details.](media/troubleshoot-app-install-03.png)

The app installation error details will indicate the problem. You can use these details to determine the best action to take to resolve the problem. For more information about troubleshooting app installation issues, see [Error Codes For Troubleshooting App Installation Issues](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> You can also access the **troubleshooting** pane by pointing your browser to: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## Next steps

- For additional Intune troubleshooting information, see [Use the troubleshooting portal to help users at your company](help-desk-operators.md). 
- Learn about any known issues in Microsoft Intune. For more information, see [Known issues in Microsoft Intune](known-issues.md).
- Need extra help? See [How to get support for Microsoft Intune](get-support.md).