---
# required metadata

title: How to add apps to Microsoft Intune | Microsoft Docs
description: These procedures help you get your apps into Intune ready to be assigned to users and devices. 
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# How to add an app to Microsoft Intune

1. In the **Apps** workload, choose **Manage** > **All Apps**.
2. Above the list of apps, choose **Add**.
3. In the **Add App** blade, choose the type of app you want to add from:
	- **Android LOB App** - 
	- **Android Store App** - 
	- **iOS LOB App** - 
	- **iOS Store App** - Search the iOS store for an app to add to Intune.
	- **iOS VPP App** - 
	- **Web App** - 
	- **Windows Store App** - 
4. When you have finished configuring the app, choose **Save**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose.

## Create an Android line of business app

### Step 1 - Specify the software setup file

1. In the **Add App** blade, choose **Software Setup File**.
2. In the **Select setup file** blade, click the browse button and browse to the Android app setup file (with the extension **.apk**), then click **OK**.

### Step 2 - Configure app information

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**.
Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in.

- **App Name** - Enter the name of the app as it will be displayed in the company portal.
Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
- **Publisher** - Enter the name of the publisher of the app.
- **Minimum Operating System** - 
- **Category** - (optional). Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
- **Information URL** - 
- **Privacy URL** - 
- **Developer** - 
- **Owner** - 
- **Notes** - 
- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

## Create an Android Store app

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**.
Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in.

- **App Name** - Enter the name of the app as it will be displayed in the company portal.
Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
- **Publisher** - Enter the name of the publisher of the app.
- **App store URL** - 
- **Minimum Operating System** - 
- **Category** - (optional). Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
- **Information URL** - 
- **Privacy URL** - 
- **Developer** - 
- **Owner** - 
- **Notes** - 
- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

## Create an iOS line of business app

### Step 1 - Specify the software setup file

1. In the **Add App** blade, choose **Software Setup File**.
2. In the **Select setup file** blade, click the browse button and browse to the iOS app setup file (with the extension **.ipa**), then click **OK**.

### Step 2 - Configure app information

2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**.
Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in.

- **App Name** - Enter the name of the app as it will be displayed in the company portal.
Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
- **Publisher** - Enter the name of the publisher of the app.
- **Applicable Device Type** - Select whether this app can be installed on iPads, iPhones, or compatible iPods.
- **Minimum Operating System** - 
- **Category** - (optional). Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
- **Information URL** - 
- **Privacy URL** - 
- **Developer** - 
- **Owner** - 
- **Notes** - 
- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

## Create an iOS store app

### Step 1 - Search for the app in the store

1. In the **Add App** blade, choose **Search the App Store**.
2. In the **Apple App Store** blade, enter the name (or part of the name) in the search box. Intune will search the store and return a list of relevant results.
3. From the list, choose the app you want, then click **OK**.

### Step 2 - Configure app information

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**.
Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in.

- **App Name** - Enter the name of the app as it will be displayed in the company portal.
Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
- **Publisher** - Enter the name of the publisher of the app.
- **App store URL** - 
- **Minimum Operating System** - 
- **Category** - (optional). Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
- **Information URL** - 
- **Privacy URL** - 
- **Developer** - 
- **Owner** - 
- **Notes** - 
- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

## Create an iOS volume-purchase program (VPP) app

<!--- This is not yet implemented in my build --->


## Create a web app

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**.

- **App URL** - Enter the URL of the web site that hosts the app you want to deploy.
- **App Name** - Enter the name of the app as it will be displayed in the company portal.
- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
- **Publisher**
- **Category**
- **Display this as a featured app in the Company Portal**
- **Require a managed browser to open this link**
- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.


## Create a Windows store app

<!--- This is not yet usable in my build --->
