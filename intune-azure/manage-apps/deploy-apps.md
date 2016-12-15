---
# required metadata

title: How to assign apps to groups with Microsoft Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Once you've added an app to Intune, you'll want to assign it to groups of users or devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/13/2016
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
#ms.custom:
---

# How to assign apps to groups with Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. In the **Mobile Apps** workload, choose **Manage** > **Apps**.
2. On the list of apps blade, click the app you want to assign.
3. On the <*app name*> - **Overview** blade, choose **Manage** > **Assignments**.
4. Choose **Select Groups** then, on the **Select groups** blade, choose the Azure AD groups to which you want to assign the app.
5. For each app you choose, choose an **assignment type** for the app from: 
	- **Available** - Users install the app from the Company Portal.
	- **Not Applicable** - The app is not installed or shown in the Company Portal.
	- **Required** - The app is installed on devices in the selected groups.
	- **Uninstall** - The app is uninstalled from devices in the selected groups.
	- **Available Without Enrollment**
6. Once you are done, choose **Save**.

The app is now assigned to the group you chose.

See [How to monitor apps](monitor-apps.md) for information to help you monitor app assignments.

