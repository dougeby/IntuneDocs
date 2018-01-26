---
# required metadata

title: Add built-in apps to mobile devices using Intune
titlesuffix: "Azure portal"
description: "Learn how you can use Intune to make it easier to install built-in apps mobile devices."
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/26/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to add built-In apps to Microsoft Intune

The **built-in** app type makes it easy for you to assign curated managed apps, such as Office 365 apps, to iOS and Android devices. You can assign specific apps for this app type, such as Excel, Power BI, SharePoint, Teams, OneDrive, Outlook, Skype, and others. After adding an app, you will see the app type as either **Built-in iOS app** or **Built-in Android app**. By using the built-in app type, you can choose which of these specific apps to provide to device users.

 In earlier editions of the Intune console, Intune provided several default managed Office 365 apps, such as Outlook and OneDrive. The app type for these managed apps were tagged as "Managed iOS Store App" or "Managed Android App". We recommend you use the Built-in app types instead of "Managed iOS Store" or "Managed Android App" as built-in app type provides additional flexibility to edit and delete office 365 apps.

>[!NOTE]
>Default Office 365 apps tagged as "Managed iOS Store" and "Managed Android App" will be removed from the app list when all assignments are deleted for this app.

## Add built-in app

The following steps allow you to add a built-in app to your available apps in Microsoft Intune.
1.	Sign into the Azure portal.
2.	Display the Microsoft Intune blade, by choosing **More Services** > **Monitoring + Management** > **Intune**.
3.	On the **Intune** blade, choose **Mobile apps**.
4.	On the **Mobile apps** blade, choose **Apps** in the **Manage** group.
5.	Choose **Add** to add a new app.
6.	On the **Add** app blade, choose **Built-In app** from the **App type** list.
7.	Click **Select app** to choose the built-in apps to include.
8.	On the Built-In app blade, select the apps to include.
9.	On the **Add app** blade, click **Add** to include the apps.


## Configure app information

You can modify information about the built-in app. This information helps you to identify the app in Intune and also helps users find the app in the Company Portal app.
1.	On the **Mobile apps - Apps** blade, choose the built-in app that you want to modify. A blade for the built-in app is displayed.
2.	Select the **Properties** option from the **Manage** group.
3.	Select the **Configure** option to modify the built-in app information.
4.	On the **App information** blade, you can modify the following information:
    -	**Name** - Enter the name of the built-in app as it is displayed in the company portal. Make sure all names that you use are unique. If the same app name exists twice, only one of the apps is displayed to users in the company portal.
    -	**Description** - Enter a description for the app. 
    -	**Publisher** - Enter the name of the publisher of the app.
    -	**Category** - Optionally, select one or more of the built-in app categories. Setting this option makes it easier for users to find the app when they browse the company portal.
    -	**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
    -	**Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
    -	**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
    -	**Developer** - Optionally, enter the name of the app developer.
    -	**Owner** - Optionally, enter a name for the owner of this app, for example, HR department.
    -	**Notes** - Enter any notes you would like to associate with this app.
    -	**Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.
3.	When you are done, click **OK** on the **App information** blade.
4.	Click **Save** on the **Properties** blade.

## Next steps

You can now assign the apps the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).
