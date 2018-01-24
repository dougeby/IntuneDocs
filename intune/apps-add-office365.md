---
# required metadata

title: Install Office 365 apps to mobile devices using Intune
titlesuffix: "Azure portal"
description: "Learn how you can use Intune to make it easier to install Office 365 apps on Windows 10 devices."
keywords:
author: barlan
ms.author: barlanmsft
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aiwang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune

This app type makes it easy for you to assign Office 365 ProPlus 2016 apps to devices you manage that run Windows 10. You can also install apps for the Microsoft Project Online desktop client, and Microsoft Visio Pro for Office 365, if you own licenses for them. The apps you want appear as a single entry in the list of apps in the Intune console.


## Before you start

>[!IMPORTANT]
>This method of installing Office is only supported if no other versions of Microsoft Office are installed on the device. We provide user help for this scenario [here](/intune-user-help/install-office-windows.md).

- Devices to which you deploy these apps must be running the Windows 10 Creators Update or later.
- Intune only supports adding Office apps from the Office 365 ProPlus 2016 suite.
- If any Office apps are open when Intune installs the app suite, end users might lose data from unsaved files.
- This installation method is not supported on Windows 10S devices.
- Intune does not support installing Office 365 desktop apps from the Microsoft Store (known as Office Centennial apps) on a device to which you have already deployed Office 365 apps with Intune. If you install this configuration, it might cause data loss or corruption.


## Get started

1.	Sign into the Azure portal.
2.	Choose **More Services** > **Monitoring + Management** > **Intune**.
3.	On the **Intune** blade, choose **Mobile apps**.
4.	In the **Mobile apps** workload, choose **Manage** > **Apps**.
5.	Above the list of apps, choose **Add**.
6.	On the **Add App** blade, choose **Office 365 ProPlus Suite (Windows 10)**.

## Configure the app suite

In this step, choose the Office apps you want to assign to devices.

1.	On the **Add App** blade, choose **Configure App Suite**.
2.	On the **Configure App Suite** blade, choose the standard Office apps that you want to assign to devices. Additionally, you can install apps for Microsoft Project Online desktop client, and Microsoft Visio Pro for Office 365 if you own licenses for them.
3.	When you are done, click **OK**.

>[!IMPORTANT]
> After you have created the app suite, you cannot edit its properties. To configure different properties, delete the app suite and create a new one.

## Configure app information

In this step, provide information about the app suite. This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.

1.	On the **Add App** blade, choose **App Suite Information**.
2.	On the **App Suite Information** blade, specify the following information:
	- **Suite Name** - Enter the name of the app suite as it is displayed in the company portal. Make sure all suite names that you use are unique. If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.
	- **Suite Description** - Enter a description for the app suite. For example, you could list the apps you've selected to include.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Category** - Optionally, select one or more of the built-in app categories, or a category you created. This makes it easier for users to find the app suite when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app suite prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.
3.	When you are done, click **OK**.

## Configure app settings

In this step, configure installation options for the app suite. The settings apply to all apps you added to the suite.

1.	On the **Add App** blade, choose **App Suite Settings**.
2.	On the **App Suite Settings** blade, specify the following information:
	- **Office version** - Choose whether you want to assign the 32-bit, or 64-bit version of Office. You can install the 32-bit version on both 32-bit, and 64-bit devices, but you can only install the 64-bit version on 64-bit devices.
	- **Update Channel** - Choose how office is updated on devices. For information about the different update channels, see Overview of update channels for Office 365 ProPlus. Choose from:
		- **Current**
		- **Deferred**
		- **First Release Current**
		- **First Release Deferred**
	- **Automatically accept the app end user license agreement** - Select this option if you don't require end users to accept the license agreement. Intune then automatically accepts the agreement.
	- **Use shared computer activation** - Shared computer activation is used when multiple users share a computer. For more information, see Overview of shared computer activation for Office 365 ProPlus.
	- **Languages** - Office automatically installs in any supported languages that are installed with Windows on the end-users device. Select this option if you want to install additional languages with the app suite.

>[!IMPORTANT]
> After you have created the app suite, you cannot edit its properties. To configure different properties, delete the app suite and create a new one.

## Finish up

When you are done, on the **Add App** blade, choose **Save**. The app you have created is displayed in the apps list.

## Error codes when installing the app suite

The following table lists common error codes you might encounter and their meaning.

### Status for Office CSP:

||||
|-|-|-|
|Status|Phase|Description|
|1460 (ERROR_TIMEOUT)|Download|Failed to download the Office Deployment Tool|	 
|13 (ERROR_INVALID_DATA)|-|Cannot verify the signature of the downloaded Office Deployment Tool|
|Error code from CertVerifyCertificateChainPolicy|-|Failed certification check for the downloaded Office Deployment Tool|	 
|997|WIP|Installing|
|0|After installation|Installation succeeded|	 
|1603 (ERROR_INSTALL_FAILURE)|-|Failed any prerequisite check, like:<br>- SxS (Tried to install when 2016 MSI is installed)<br>- version mismatch<br>- etc.|	 
|0x8000ffff (E_UNEXPECTED)|-|Tried to uninstall when there is no Click-to-run Office on the machine.|	 
|17002|-|Failed to complete the scenario (install). Possible reasons:<br>- Install canceled by user<br>- Install canceled by another installation<br>- Out of disk space during installation<br>- Unknown language ID|
|17004|-|Unknown SKUs|	 


### Office Deployment Tool Error Codes

|||||
|-|-|-|-|
|Scenario|Return code|UI|Note|
|Uninstall effort when there is no active Click-to-run installation|-2147418113, 0x8000ffff or 2147549183|Error Code: 30088-1008<br>Error Code: 30125-1011 (404)|Office Deployment Tool|
|Install when there is MSI version installed|1603|-|Office Deployment Tool|
|Installation canceled by user, or by another installation|17002|-|Click-to-run|
|Try to install 64-bit on a device that has 32-bit installed.|1603|-|Office Deployment Tool return code|
|Try to install an unknown SKU (not a legitimate use case for Office CSP since we should only pass in valid SKUs)|17004|-|Click-to-run|
|Lack of space|17002|-|Click-to-run|
|The click-to-run client failed to start (unexpected)|17000|-|Click-to-run|
|The click-to-run client failed to queue scenario (unexpected)|17001|-|Click-to-run|

## Next steps

You can now assign the apps the groups you choose. For help, see [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps).
