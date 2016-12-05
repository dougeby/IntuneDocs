---
# required metadata

title: How to assign apps to groups with Microsoft Intune | Intune Azure preview | Microsoft Docs
description: Once you've added an app to Intune, you'll want to assign it to groups of users or devices.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
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

1. In the **Mobile Apps** workload, choose **Manage** > **All Apps**.
2. On the list of apps blade, select the app you want to assign, then choose '**...**' > **Assign Groups**.
3. On the <*app name*> - **Groups Assigned** blade, choose **Manage** > **Groups Assigned**.
4. Choose **Assign Groups** then, on the **Select groups** blade, choose the Azure AD groups to which you want to assign the app.
5. For each app you choose, choose an **assignment type** for the app from: 
	- **Available**
	- **Not Applicable**
	- **Required**
	- **Uninstall**
	- **Available Without Enrollment**
6. Once you are done, choose **Save**.

See [How to monitor apps](monitor-apps.md) for information to help you monitor app assignments.

