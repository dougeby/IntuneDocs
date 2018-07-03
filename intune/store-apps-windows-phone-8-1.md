---
# required metadata

title: Add Windows Phone 8.1 store apps to Microsoft Intune
titleSuffix: 
description: Learn about adding Windows Phone 8.1 store apps to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Add Windows Phone 8.1 store apps to Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Before you assign an app to a device or a group of users, you must first add the app to Microsoft Intune. 

## Add an app to Intune
You can add a Windows Phone 8.1 store app to Intune from the Azure portal by doing the following:

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**.  
    Intune is located in the **Monitoring + Management** section.
3. In the **Intune** pane, select **Mobile apps**.
4. In the **Mobile apps** workload pane, under **Manage**, select **Apps**.
5. In the **Apps** pane, select **Add**.
6. In the **Add app** pane, select an **App type** of **Windows Phone 8.1**, and then select **App information**.
7. In the **App information** pane, add the app information. Depending on the app you have chosen, some of the values in this pane might have been automatically filled in:
	- **Name**: Enter the name of the app as it is to be displayed in the company portal. Make sure that any app name that you use is unique. If an app name is duplicated, only one name is displayed to users in the company portal.
	- **Description**: Enter a description for the app. This description is displayed to users in the company portal.
	- **Publisher**: Enter the name of the publisher of the app.
	- **Appstore URL**: Type the App Store URL of the app that you want to create.
	- **Category**: Optionally, select one or more of the built-in app categories, or a category that you created. Doing so makes it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal**: Select this option to display the app suite prominently on the main page of the company portal when users browse for apps.
	- **Information URL**: Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL**: Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer**: Optionally, enter the name of the app developer.
	- **Owner**: Optionally, enter a name for the owner of this app, for example, *HR department*.
	- **Notes**: Optionally, enter any notes that you want to associate with this app.
	- **Logo**: Optionally, upload an icon that will be associated with the app. This icon is displayed with the app when users browse the company portal.
8. Select **OK**.
9. Select **Add**.

The app that you've created is displayed in the apps list, where you can assign it to the groups that you select.

## Next steps

- [Assign apps to groups](apps-deploy.md)
