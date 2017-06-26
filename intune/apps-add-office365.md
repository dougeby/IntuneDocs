---
# required metadata

title: Install Office 365 apps on Windows 10 devices using Intune
titleSuffix: "Intune on Azure"
description: "Learn how you can use Intune to make it easier to install Office 365 apps on Windows 10 devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
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

# How to add Office 365 apps for Windows 10 to Microsoft Intune

This app type makes it easy for you to assign Office 365 ProPlus apps to devices that you manage which run Windows 10. Additionally, you can also install Microsoft Project, and Microsoft Visio, if you own licenses for them. The apps you want are bundled together and appear as one app in the list of apps in the Intune console.


##Before you start


- This method of installing Office is only supported if no other versions of Microsoft Office are installed on the device.
- If you do install Office on a device that already has Office installed, read the following considerations:
	- Regardless of the version of Office you use, you cannot install 32-bit and 64-bit Office products on the same device.
	- You cannot install the same version of the Click-to-run, and MSI versions of Office on the same device but you can install different major versions.
	- If you already have an earlier version of Office that you installed using Click-To-Run, you must remove any apps that you want to replace with the newer version. For example, if you have an older version of Word on the device, and want to assign the latest version, you must remove the old version first.
	- If a device already has Office 365 installed, assigning the Office 365 ProPlus bundle to the device might mean you have to change your Office subscription level.
	- Devices to which you deploy these apps must be running the Windows 10 Creators Update or later.

## Get started

1.	Sign into the Azure portal.
2.	Choose **More Services** > **Monitoring + Management** > **Intune**.
3.	On the **Intune** blade, choose **Manage apps**.
4.	In the **Mobile apps** workload, choose **Manage** > **Apps**.
5.	Above the list of apps, choose **Add**.
6.	On the **Add App** blade, choose **Office 365 ProPlus Suite (Windows 10)**.

## Configure the app bundle

In this step, choose the Office apps you want to assign to devices.

1.	On the **Add App** blade, choose **Configure App Bundle**.
2.	On the **Configure App Bundle** blade, choose the standard Office apps that you want to bundle together and assign to devices. Additionally, you can install apps for Microsoft Visio and Microsoft Project if you own licenses for them.
3.	When you are done, click **OK**.

## Configure app information

In this step, provide information about the app bundle. This information helps you to identify it in the Intune console, and also help end users to find it in the Company Portal app.

1.	On the **Add App** blade, choose **App Information**.
2.	On the **App Information** blade, specify the following information: 
	- **Bundle Name** - Enter the name of the app bundle as it is displayed in the company portal. Make sure all bundle names that you use are unique. If the same bundle name exists twice, only one of the apps is displayed to users in the company portal.
	- **Bundle Description** - Enter a description for the app bundle. For example, you could list the apps you've selected to include.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Category** - Optionally, select one or more of the built-in app categories, or a category you created. This makes it easier for users to find the app bundle when they browse the company portal.
	- **Display this bundle as a featured app in the Company Portal** - Display the app bundle prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.
3.	When you are done, click **OK**.

>[!IMPORTANT]
> After you have created the app bundle, you cannot edit its properties. To configure different properties, delete the app bundle and create a new one.

## Configure app settings

In this step, configure installation options for the app bundle. The settings apply to all apps you added to the bundle.

1.	On the **Add App** blade, choose **App Settings**.
2.	On the **App Settings** blade, specify the following information: 
	- **Office version** - Choose whether you want to assign the 32-bit, or 64-bit version of Office. You can install the 32-bit version on both 32-bit, and 64-bit devices, but you can only install the 64-bit version on 64-bit devices.
	- **Update Channel** - Choose how office is updated on devices. For information about the different update channels, see Overview of update channels for Office 365 ProPlus. Choose from: 
		- **Current**
		- **Deferred**
		- **First Release Current**
		- **First Release Deferred**
	- **Automatically accept the app end user license agreement** - Select this option if you don't require end users to accept the license agreement. Intune then automatically accepts the agreement.
	- **Use shared computer activation** - Shared computer activation is used when multiple users share a computer. For more information, see Overview of shared computer activation for Office 365 ProPlus.
	- **Languages** - Office automatically installs in any supported languages that are installed with Windows on the end-users device. Select this option if you want to install additional languages with the bundle.

## Finish up

When you are done, on the **Add App** blade, choose **Save**. The app you have created is displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps).


## Error codes when installing the app bundle

The following table lists common error codes you might encounter and their meaning.

### Status for Office CSP: 

|||||
|-|-|-|-|
|Status|Phase|Description|Note 
|1460 (ERROR_TIMEOUT)|Download|Failed to download the Office Deployment Tool|	 
|13 (ERROR_INVALID_DATA)|-|Cannot verify the signature of the downloaded Office Deployment Tool|-| 	 
|Error code from CertVerifyCertificateChainPolicy|-|Failed certification check for the downloaded Office Deployment Tool|-| 	 
|997|WIP|Installing|-|	 
|0|After installation|Installation succeeded|-| 	 
|1603 (ERROR_INSTALL_FAILURE)|-|Failed any prerequisite check, like:<br>- SxS (Tried to install when 2016 MSI is installed)<br>- version mismatch<br>- etc.|-| 	 
|0x8000ffff (E_UNEXPECTED)|-|Tried to uninstall when there is no Click-to-run Office on the machine.|- |	 
|17002|-|Failed to complete the scenario (install). Possible reasons:<br>- Install canceled by user<br>- Install canceled by another installation<br>- Out of disk space during installation<br>- Unknown language ID|-|	 
|17004|-|Unknown SKUs|-|	 


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
 	 	 	 


