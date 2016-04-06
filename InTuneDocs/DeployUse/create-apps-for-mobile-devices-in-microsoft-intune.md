---
title: Create apps for mobile devices|Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: robstackmsft
---
# Deploy apps to mobile devices in Microsoft Intune

Use the information in this topic to learn about the three steps for Microsoft Intune app deployment; configuration, deployment, and monitoring. If you want to learn some of the basic concepts for app deployment, see [Plan for app deployment in Microsoft Intune](../PlanDesign/plan-for-app-deployment-in-microsoft-intune.md).


> [!IMPORTANT]
> The information in this topic helps you to deploy apps to [enrolled Windows PCs](https://technet.microsoft.com/library/mt346003.aspx) and other enrolled devices. If you want to deploy apps to [Windows PCs that you manage using the client software](https://technet.microsoft.com/library/dn646959.aspx), see [Deploy apps to Windows PCs in Microsoft Intune](../Topic/Deploy-apps-to-Windows-PCs-in-Microsoft-Intune.md).

## Create the app
You use the Intune Software Publisher to configure the properties of the app and, where applicable, upload it to your cloud storage space.

### To create an app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Apps** &gt; **Add Apps** to start the Intune software publisher.

    > [!TIP]
    > You might need to enter your Intune username and password before the publisher starts.

2.  On the **Software setup** page of the software publisher, choose one of the following options for **Select how this software is made available to devices**:
	- **Software installer**, for apps with the extension **.msi**, or **.exe**, specify:
		- **Select the software installer file type** - This indicates the type of software you want to deploy. For example, if you want to install an iOS app, choose **App Package for iOS (&#42;.ipa file)**.
        - **Specify the location of the software setup files** - Enter the location of the installation files or click **Browse** to select the location from a list.
        - **Include additional files and subfolders from the same folder** - For the **Windows Installer** file type only.<br>Some software that uses Windows Installer requires supporting files which are typically found in the same folder as the installation files. Select this option if you also want to deploy these files.<br>This installation type uses some of your cloud storage space.

  -   **External link**, for apps you want to create by specifying a link to an app store, specify:

		- **Specify the URL** - Specify the URL of one of the following:
			- The app store URL of the app you want to deploy. For example, if you want to deploy the Microsoft Remote Desktop app for Android, specify **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**. To find the URL of the app, use a search engine to find the store page containing the app. For example, to find the Remote Desktop app, you could search **Microsoft Remote Desktop Android**.
			- A web site. Intune will deploy a shortcut icon to the site to the device (known as a web clip).
			- An app on the web. Intune will deploy a shortcut icon to the app on the device.
        - **Require a managed browser to open this link (Android and iOS only)**|When you deploy a link to a website or web app to users, they will only be able to open it in the Intune managed browser which must be installed on their device.<br>For more details about the managed browser, see [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies-with-microsoft-intune.md).<br>This installation type does not use any of your cloud storage space.

  -   **Managed iOS app from the app store**, for free apps from the iTunes store that you want to manage with MAM policies, specify:

		- **Specify the URL** - Enter the app store URL of the app you want to deploy. For example, if you want to deploy the Microsoft Work Folders app for iOS, specify **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**.<br>This installation type does not use any of your cloud storage space.

		For example, if you want to deploy the Microsoft Word app from the iTunes store to devices, the page would look like this:
		
		![Intune Software Publisher](./media/publisher-for-mobile.png)

3.  On the **Software description** page, configure the following:

    > [!TIP]
    > Depending on the installer type you are using, some of these values might have been automatically entered, or might not appear.

	- **Publisher** - Enter the name of the publisher of the app.|
    - **Name** - Enter the name of the app as it will be displayed in the company portal.<br>Make sure all app names you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
    - **Description** - Enter a description for the app. This will be displayed to users in the company portal.|
    - **URL for software information** - Available only if you selected **Software installer**. Optionally enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
    - **Privacy URL** - Available only if you selected **Software installer**. Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.|
    - **Category** - (optional) Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
    - **Display this as a featured app and highlight it in the company portal** - Display the app prominently on the main page of the company portal when users browse for apps.
    - **Icon** - (optional) Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

		In this example, you configured a description for the Microsoft Word app for iOS:

		![Software description example](./media/ios-software-description.png)

4.  On the **Requirements** page, select the requirements that must be met before the app can start to install on a device. For example, for an app package for iOS, you can select the minimum version of iOS required, and the type of device it must be, like an iPhone, or an iPad.

    > [!TIP]
    > The **Requirements** page is not displayed for all types of apps.

5.  Further wizard pages are displayed when you choose the **Windows Installer** file type. This file type is used when you deploy software to PCs running Windows 10 or later that are enrolled with Intune.

6.  On the **Summary** page, review the information you specified. Once you are ready, click **Upload**.

7.  Click **Close** to finish.

The app is displayed on the **Apps** node of the **Apps** workspace.


## Next steps

Once you've created an app, the next step is to deploy it. To find out more, see [Deploy apps in Microsoft Intune.md](deploy-apps-in-microsoft-intune.md)



