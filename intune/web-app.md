---
# required metadata

title: How to add web apps to Microsoft Intune
titleSuffix: 
description: Learn about adding web apps to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add web apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune supports a variety of app types including web apps. A web app is a client-server application. The server provides the web app, which includes the UI, content, and functionality. Additionally, modern web hosting platforms commonly offer security, load balancing, and other benefits. A web app is separately maintained on the Web. You use Microsoft Intune to point to this app type. You also assign which groups of users can access this app. 

Before you can manage and assign an app for your users, add the app to Intune. Intune creates a shortcut to the web app on the user's device home screen.

> [!Note]
> Web apps are not supported on Android for Work devices and macOS.

Complete the following steps to add an app to Intune as a shortcut to an app on the web:

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Microsoft Intune** pane, select **Mobile apps**.
4. On the **Mobile apps** pane, select **Apps**.
5. Above the list of apps, select **Add**. The **Add app** pane is displayed.
6. In the **Add app** pane, select the **Web link** type from the **App type** drop-down list.
7. Select the **Configure** option to display the **App information** pane.
8. In the **App information** pane, add the following information:
	- **Name** - Enter the name of the app as it is to be displayed in the company portal.
	- **Description** - Enter a description for the app. This is displayed to end users in the company portal.
	- **Publisher** - Enter the name of the publisher of this app.
	- **App URL** - Enter the URL of the web site that hosts the app you want to assign.
	- **Category (optional)** - Select one or more of the built-in app categories, or a category you created. This selection can make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Require a managed browser to open this link** - When you assign a link to a website or web app to users, they can open it in the Intune managed browser. This browser must be installed on their device.
	- **Logo** - Upload a logo that is associated with the app. This logo is the logo that is displayed with the app when users browse the company portal.
9. When you are done, on the **Add information** pane, select **Ok**.
10. Then, from the **Add app** pane, select **Add**.

> [!Note]
> Users need to add the Intune widget to their home screen to display web apps that have been assigned to Android devices.

## Next steps

- The app you have created is displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).