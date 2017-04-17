---
title: Help desk troubleshooting console
titleSuffix: "Intune Azure preview"
description: A console for help desk support staff in Microsoft Intune
keywords:
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/17
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sumitp
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---
# Troubleshooting console in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As an IT administrator, you can give users permission to view a help desk troubleshooting console that can help resolve issues for end users. The following topic explains how to enable help desk users to view the Troubleshooting blade in Intune and provides an overview of the blade.

Help desk users can view the Troubleshoot workspace in the Intune console but cannot perform other administrative tasks or view other workspaces.

## Add help desk users

Help desk users are Intune users with permission to view the Troubleshoot workspace in the Intune console.

1. As an Intune administrator, login to the [Azure portal](https:portal.azure.com), select **More Services** > **Monitoring + Management** > **Intune**.
2. In the left navigation blade, select **Intune roles**.
3. Click **Select user** and then select one or more users to give help desk permissions.
4. Click **Select**. Selected users now have help desk permissions in Intune.

## Access the Troubleshoot console

Help desk users can access the Troubleshoot workspace in two ways:
- In the [Azure portal](https:portal.azure.com), select **More Services** > **Monitoring + Management** > **Intune**, and then in the left navigation blade, select **Troubleshoot**. Other workspaces are visible in the left navigation pane, but unavailable.![Screenshot of the Intune Troubleshoot workspace with Select User link](media/help-desk-user.png)

- Open [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in a web browser. Only the Troubleshoot console is visible.

## Use the Troubleshoot console

The helpdesk user can select a user to troubleshoot by clicking **Select User**. User information can be used to help understand the current state of users and their devices.

Help desk users can use the Troubleshoot console to view the following Intune users and devices details:
- User account information
- User group membership
- Device details

Help desk users can also perform remote tasks on devices such as **Remote lock**.
