---
# required metadata

title: Monitor app deployments| Microsoft Intune
description: Learn how to monitor apps you deployed with Intune.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Monitor app deployments in Microsoft Intune

## Monitor an app deployment
You can see the apps you manage, and the status of any deployments in the Intune administration console.

### To view the apps you manage and their status
In the **Apps** workspace, click the **Apps** node, then click **Apps**.

The list of apps you manage is displayed. You can click on any app to see an installation status in the lower pane of the console windows. Click on this status to see further details. For example, if the status shows **1 user has this software available**, you can click the message to see the name of the user.

> [!TIP]
> You can use the **Filters** drop-down list to show only apps that meet the criteria you specify, like apps that failed to install, or apps that were successfully deployed.
> 
> ![App filters example](./media/app-filters.png)

Additionally, the **Dashboard** workspace shows an overview of the status of your apps. If you click anywhere in the overview, you'll be taken to the list of apps.

## To view more detailed information about an app
In the list of apps, select any app, and then click **View Properties**.

On the **Software Properties** page for the app, click one of these tabs: **General** - Shows general information about the app and it's installation status, **Devices** - Shows the devices that successfully installed a targeted deployment of the app, **Users** - Shows the users who's devices successfully installed a targeted deployment of the app.

As before, you can use the **Filters** drop-down list to configure the values shown on each of the tabs.



