---
# required metadata

title: Add a Windows line-of-business app to Microsoft Intune
titlesuffix:
description: Learn how to add a Windows line-of-business app to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Add a Windows line-of-business app to Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A line-of-business (LOB) app is one that you add from an app installation file. This kind of app is typically written in-house. The following steps provide guidance to help you add a Windows LOB app to Microsoft Intune.

## Step 1: Specify the software setup file

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**. Intune is in the **Monitoring + Management** section.
3. In the **Intune** pane, select **Mobile apps**.
4. In the **Mobile apps** workload, select **Manage** > **Apps**.
5. Above the list of apps, select **Add**.
6. In the **Add app** pane, select **Line-of-business app**.

## Step 2: Configure the app package file

1. In the **Add app** pane, select **App package file**.
2. In the **App package file** pane, select the browse button. Then select a Windows installation file with the extension **.msi**, **.appx**, or **.appxbundle**.
3. When you're finished, select **OK**.


## Step 3: Configure app information

1. In the **Add app** pane, select **App information**.
2. In the **App information** pane, configure the following information. Some of the values in this pane might be automatically filled in.
	- **Name**: Enter the name of the app as it appears in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps appears in the company portal.
	- **Description**: Enter a description for the app. The description appears in the company portal.
	- **Publisher**: Enter the name of the publisher of the app.
	- **Ignore app version**: Set to **Yes** if the app developer automatically updates the app.
	- **Category**: Select one or more of the built-in app categories, or select a category that you created. Categories make it easier for users to find the app when they browse through the company portal.
	- **Display this as a featured app in the Company Portal**: Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL**: Optionally, enter the URL of a website that contains information about the app. The URL appears in the company portal.
	- **Privacy URL**: Optionally, enter the URL of a website that contains privacy information for the app. The URL appears in the company portal.
	- **Command-line arguments**: Optionally, enter any command-line arguments that you want to apply to the .msi file when it runs. An example is **/q**.
	- **Developer**: Optionally, enter the name of the app developer.
	- **Owner**: Optionally, enter a name for the owner of this app. An example is **HR department**.
	- **Notes**: Enter any notes that you want to associate with this app.
	- **Logo**: Upload an icon that is associated with the app. The icon is displayed with the app when users browse through the company portal.
3. When you're finished, select **OK**.

## Step 4: Finish up

1. In the **Add app** pane, verify that you configured the app information correctly.
2. Select **Add** to upload the app to Intune.

## Step 5: Update a line-of-business app

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## Configure a self-updating mobile MSI app to ignore the version check process

You can configure a known self-updating mobile MSI app to ignore the version check process. 

Some MSI installer-based apps are automatically updated by the app developer. For these automatically updated MSI apps, you can configure the **Ignore app version** setting in the **App information** pane. When you switch this setting to **Yes**, Microsoft Intune will not enforce the app version that's installed on the Windows client. 

This capability is useful to avoid getting into a race condition. For instance, a race condition can occur when the app is automatically updated by the app developer and is updated by Intune. Both might try to enforce a version of the app on a Windows client, which creates a conflict.

## Next steps

- The app that you created appears in the list of apps. You can now assign it to groups that you choose. For help, see [How to assign apps to groups](apps-deploy.md).

- Learn more about the ways in which you can monitor the properties and assignment of your app. See [How to monitor app information and assignments](apps-monitor.md).

- Learn more about the context of your app in Intune. See [Overview of device and app lifecycles](introduction-device-app-lifecycles.md).
