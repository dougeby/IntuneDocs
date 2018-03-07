---
# required metadata

title: How to add apps to Microsoft Intune
titlesuffix:
description: Learn how to add apps to Microsoft Intune so you can assign apps to users and devices. Intune supports a wide range of different app types.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
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
ms.custom: intune-azure
---

# How to add an app to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Before you can assign, monitor, configure, or protect apps, you must add them to Microsoft Intune.

The users of apps and devices at your company (your company's workforce) may have several app requirements. Before adding apps to Intune and making them available to your workforce, you must assess and understand a few app fundementals. You must understand the different types of apps available for Intune. You will need to assess the app requirements, such as the the needed platforms and capabilities needed for your workforce. Also, you must determine whether you will use Intune to manage the devices (including apps), or have Intune manage apps without managing devices. You must determine who in your workforce will need different apps and different capabilities. The information provided in this article will help you get started.

## App types in Microsoft Intune

Intune supports a wide range of different app types. The available options differ for each app type. Intune lets you add and assign these app types:

| App Types                                 	| Installation                                                               	| Updates                   	|
|------------------------------------------	|----------------------------------------------------------------------------	|---------------------------	|
| Apps from the store (store apps)         	| Intune installs the app on the   device                                    	| App updates are automatic 	|
| Apps written in-house (line-of-business) 	| Intune installs the app on the   device (you supply the installation file) 	| You must update the app   	|
| Apps that are built-in (built-in apps)   	| Intune installs the app on the   device                                    	| App updates are automatic 	|
| Apps on the web (web link)               	| Intune creates a shortcut to the   web app on the device home screen       	| App updates are automatic 	|

### Specific app type details
 
The following table lists the specific app types in Microsoft Intune.

| **App   Specific Type**                         | **General App Type**             | **App Specific Procedures**                                                                                                                                                 |
|---------------------------------------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android   store apps                        | Store   app                  | Select **Android** as the **app type** and enter the Google   Play store URL for the app.                                                                                       |
| iOS   store apps                            | Store   app                  | Select **iOS** as the **app type**, search for the app, and   select the app within Intune.                                                                                     |
| Windows   Phone 8.1 store apps              | Store   app                  | Select **Windows Phone 8.1** as the **app type** and enter the   Microsoft store URL for the app.                                                                               |
| Microsoft   store apps                      | Store   app                  | Select **Windows** as the **app type** and enter the   Microsoft store URL for the app.                                                                                         |
| Android   for Work apps                     | Store   app                  | Find   and approve the Android for Work app from the Google Play for Work store.                                                                                        |
| Office   365 apps for Windows 10            | Store   app (Office 365)     | Select **Windows 10** under the **Office 365 Suite** as the **app type**, then select the Office 365   app that you want to install.                                                |
| Office   365 apps for macOS                 | Store   app (Office 365)     | Select **macOS** under the **Office 365 Suite** as the **app type** and then select the   Office 365 app suite.                                                                     |
| Android   line-of-business (LOB) apps       | Line-of-business   (LOB) app | Select **Line-of-business** app as   the **app type**,   select the **App package file**, and then enter an Android installation file with the   extension **.apk**.                    |
| iOS   line-of-business (LOB) apps           | Line-of-business   (LOB) app | Select **Line-of-business** app as   the **app type**,   select the **App package file**, and then enter an iOS installation file with the   extension **.ipa**.                        |
| Windows   Phone line-of-business (LOB) apps | Line-of-business   (LOB) app | Select **Line-of-business** app as   the **app type**,   select the **App package file**, and then enter an iOS installation file with the   extension **.xap**.                        |
| Windows   line-of-business (LOB) apps       | Line-of-business   (LOB) app | Select Line-of-business app as   the app type,   select the App package file, and then enter an iOS installation file with the   extension **.msi**, **.appx**, or **.appxbundle**. |
| Built-in   iOS app                          | Built-in   app               | Select **Built-In app** as the **app type** and then select the   bulit-in app from the list of provided apps.                                                                  |
| Built-in   Android app                      | Built-in   app               | Select **Built-In app** as the **app type** and then select the   bulit-in app from the list of provided apps.                                                                  |
| Web   apps                                  | Web   app                    | Select **Web link** as the **app type** and enter a valid URL   pointing to the Web app.                                                                                        |


   
You can add an app in Microsoft Intune by selecting **Mobile apps** > **Apps** > **Add**. The **Add app** blade will be displayed and allow you to select the **App type**. 

>[!TIP]
> A line-of-business (LOB) app is one that you add from an app installation file. For example, to install an iOS LOB app, you add the application by choosing **Line-of-business app** as the **App type** from the **Add app** blade. Then, select the app package file (extension .ipa). These types of apps are typically written in-house.

## Assess app requirements
As an IT Admin, not only must you determine which apps your group must use, but you must determine the capabilities needed for each group and subgroup. For each app, you must determine the platforms needed, the groups of users that need the app, the configuration policies to apply for those groups, and the protection policies to apply.  

Additionally, you must determine whether you need to focus on Mobile Device Management (MDM) or only Mobile Application Management (MAM). Using Intune to manage the device (Mobile Device Management) is useful when:
- Users need a WiFi or a VPN corporate connectivity profile to be productive.
- Users need a set of apps to be pushed to their device.
- Your organization needs to comply with regulatory or other policies that call out specific Mobile Device Management (MDM) controls, such as security or encryption.

Using Intune to manage apps (Mobile Application Management) without managing the device is useful when:
- You want to allow users to use their own device (BYOD).
- You want to provide a one-time pop-up to let users know MAM protections are in place, rather than continual device-level notification.
- You want to comply with policies that require less management capabilities on personal devices. For instance, you want to manage the corporate data for the apps, rather than manage the corporate data for the entire device.

For more information, [Compare MDM and MAM](byod-technology-decisions.md).

### Determine who will use the app

When determining the required apps your workforce needs, consider the different groups of users who use different apps. Knowing these groups is also helpful after you have added an app. Once you have added an app, you assign a group of users that can use the app. First, you must determine the appropriate group that should have access to the app based on the sensitivity of the data the app contains. You may need to include or exclude certain types of roles within your organization. For example, only certain LOB apps may be required for your sales group, whereas people focused on engineering, finance, HR, or legal may not need to use the LOB apps. In addition, your sales group may need additional data protection and access to internal corporate services on their mobile devices. You must determine how this group will connect to resources using the app. Will the data the app accesses live in the cloud or on-premise? Also, how will the users connect to resources using the app. Intune also supports enabling access to mobile apps that require secure access to on-premises data, such as line-of-business app servers. This type of access is typically done using [Intune-managed certificates](certificates-configure.md) for access control, combined with a standard VPN gateway or proxy in the perimeter such as Microsoft Azure Active Directory Application Proxy. Intune’s [App Wrapping Tool and App SDK](apps-prepare-mobile-application-management.md) can help contain the accessed data within your line-of-business app, so that it can’t pass corporate data to consumer apps or services.

Use the [Intune deployment planning, design and implementation guide](planning-guide.md) to help determine how you identify the organizational groups that are associated with each use-case and sub-use-case app scenario. For details about assigning apps to groups, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

### Determine the type of app for your solution

You can choose between the following app types:
- **Apps from the store** - A store app is an app that has been uploaded to either the Microsoft store, the iOS store, or Android store. The provider of the store app maintains and provides updates to the app. You select the app from the store list and add it using Intune as an available app for your users.
- **Apps written in-house (line-of-business)** - Apps created in-house are line-of-business (LOB) apps. The functionality of this type of app has been created for one of the Intune supported platforms, such as Windows, iOS, or Android. Your organization creates and provides you with updates as a separate file. You provide updates of the app to users by adding and deploying the updates using Intune.
- **Apps on the web** - A web app is a client-server application. The server provides the web app, which  includes the UI, content, and functionality. Additionally, modern web hosting platforms commonly offer security, load balancing, and other benefits. This type of app is separately maintained on the Web. You use Intune to point to this app type. You also assign which groups of users can access this app. Note that Android does not support web apps.

When determining the needed apps for your organization, consider how these apps integrate with cloud services, what data the apps access, whether the apps are available to BYOD users, and whether the apps require internet access.

For more information about determining the type of apps your organization needs, see **Apps** within the **Feature requirements** section of [Create a design](planning-guide-design.md#feature-requirements).

### Understanding app management and protection policies
Intune lets you modify the functionality of apps that you deploy to help align them with your company's compliance and security policies. This control allows you to determine how your company data is protected. Intune-managed apps are enabled with a rich set of mobile application protection policies, such as:

- Restricting copy-and-paste and save-as functions
- Configuring web links to open inside the Intune Managed Browser app
- Enabling multi-identity use and app-level conditional access

Intune-managed apps can also enable app protection without requiring enrollment, giving you the choice to apply data loss prevention policies without managing the user's device. Additonally, you can incorporate mobile app management in your mobile and line-of-business apps using the Intune App software development kit and app wrapping tool. For more inforamtion about these tools, see [Intune App SDK overview](app-sdk.md).

### Understanding licensed apps
In addition to web apps, store apps, and LOB apps, you should also be aware of the destintion of volume-purchase-program apps and licensed apps, such as:     
- **Apple Volume Purchasing Program for Business (iOS and MacOS)** - The iOS app store lets you purchase multiple licenses for an app that you want to run in your company. Purchasing multiple copies helps you to efficiently manage apps in your company. For more information, see [Manage iOS volume-purchased apps](vpp-apps-ios.md).
- **Android for Work (Android)** - You assign apps to Android for Work devices in a different way than you assign them to standard Android devices. All apps you install for Android for Work come from the Google Play for Work store. You log on to the store, browse for the apps you want, and approve them. The app then appears in the Licensed apps node of the Azure portal. From here, you can manage assignment of the app in the same way you would assign any other app.
- **Microsoft Store for Business (Windows 10)** - The Microsoft Store for Business gives you a place to find and purchase apps for your organization, individually, or in volume. By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Azure portal. For more information, see [Manage apps from Microsoft Store for Business](windows-store-for-business.md).

## Before you add apps
Consider the following points before you begin to add and assign apps.

- When you add and assign an app from a store, end users must have an account with that store in order to be able to install the app.
- Some apps or items you assign might be dependent on built-in iOS apps. For example, if you assign a book from the iOS store, then the iBooks app must be present on the device. If you have removed the iBooks built-in app, you cannot use Intune to reinstate it.

## Cloud storage space
All apps that you create by using the software installer installation type (for example, a line-of-business app) are packaged and uploaded to Intune cloud storage. A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates. A full subscription includes 20 GB of storage space.

You can purchase additional storage for Intune using your original purchase method. If you paid by invoice or credit card, visit the [Subscription Management portal](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions). Otherwise, contact your partner or sales associate.

Requirements for cloud storage space are as follows:

-   All app installation files must be in the same folder.
-   The maximum file size for any file that you upload is 2 GB.

## How to create and edit categories for apps

App categories can be used to help you sort apps to make them easier for users to find in the company portal. You can assign one or more categories to an app, for example, **Developer apps**, or **Communication apps**.
When you add an app to Intune, you are given the option to select the category you want. Use the platform-specific topics to add an app, and assign categories. To create and edit your own categories, use the following procedure:

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **App categories** from the **Setup** section. 
5. On the **App categories** blade, a list of the current categories is shown. Choose one of the following actions:
	- **Create a category** - Select **Add** to display the **Create category** blade, then add a name for the new category. Names can be entered in one language only, and are not translated by Intune. When you are done, click **Create**.
	- **Edit a category** - For any category in the list, choose '**...**'. This option displays a pop-up menu allowing you to **Pin to dashboard** or **Delete** the category.

## Apps added automatically by Intune

Previously, Intune contained a number of built-in apps that you could quickly assign. Based on your feedback, this list was removed and you will no longer see built-in apps.
However, if you have already assigned any built-in apps, these apps will still be visible in the list of apps. You can continue to assign these apps as required.

## Next steps

Choose one of the following topics to find out how to add apps for each platform to Intune:

- [Android store apps](store-apps-android.md)
- [Android LOB apps](lob-apps-android.md)
- [iOS store apps](store-apps-ios.md)
- [iOS LOB apps](lob-apps-ios.md)
- [Web apps (for all platforms)](web-app.md)
- [Windows Phone 8.1 store apps](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB apps](lob-apps-windows-phone.md)
- [Microsoft store apps](store-apps-windows.md)
- [Windows LOB app](lob-apps-windows.md)
- [Office 365 apps for Windows 10](apps-add-office365.md)
- [Office 365 apps for macOS](apps-add-office365-macos.md)
- [Built-in apps](apps-add-built-in.md)
