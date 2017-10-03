---
# required metadata

title: How to add Android line-of-business apps to Intune
titlesuffix: "Azure portal"
description: Learn about adding Android line-of-business apps to Intune."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Android line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## Step 1 - Specify the software setup file

[!INCLUDE[shared-proc-openintuneazure](./includes/shared-proc-openintuneazure.md)] 
2. On the **Intune** blade, choose **Manage apps**.
3. In the **Mobile apps** workload, choose **Manage** > **Apps**.
4. Above the list of apps, choose **Add**.
5. In the **Add App** blade, choose **Line-of-business app**.

## Step 2 - Configure the app package file

1. On the **Add app** blade, choose **App package** file.
2. On the **App package** file blade, choose the browse button, and select an Android installation file with the extension **.apk**.
3. When you are finished, choose **OK**.


## Step 3 - Configure app information

1. On the **Add app** blade, choose **App package** file.
2. On the **App information** blade, configure the following information. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **Description** - Enter a description for the app. This will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
	- **Category** - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
3. When you are finished, choose **OK**.

## Step 4 - Finish up

1. On the **Add app** blade, verify the information you configured is correct.
2. Choose **Add**, to upload the app to Intune.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).

## Step 5 - Update a line of business app

<!-- [!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)] -->

## Next steps

XXX
