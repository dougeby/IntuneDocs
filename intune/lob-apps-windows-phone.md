---
# required metadata

title: How to add Windows Phone line-of-business apps to Intune 
titlesuffix: "Azure portal"
description: Learn about adding Windows Phone line-of-business apps to Intune."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Windows Phone line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## Step 1 - Specify the software setup file

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Line-of-business app**.

## Step 2 - Configure the app package file

1. On the **Add app** blade, choose **App package** file.
2. On the **App package** file blade, choose the browse button, and select a Windows Phone installation file with the extension, **.xap**.
3. When you are finished, choose **OK**.


## Step 3 - Configure app information

1. On the **Add app** blade, choose **App package** file.
2. On the **App information** blade, configure the app information. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **Name** - Enter the name of the app as it is displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps is displayed to users in the company portal.
	- **Description** - Enter a description for the app. The description is displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Category** - Select one or more of the built-in app categories, or a category you created. Using categories makes it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon that is associated with the app. This icon is displayed with the app when users browse the company portal.
3. When you are finished, choose **OK**.

## Step 4 - Finish up

1. On the **Add app** blade, verify that you configured the information correctly.
2. Choose **Add**, to upload the app to Intune.

## Next steps

The app you have created are displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).
