---
# required metadata

title: How to create custom VPN profiles with Microsoft Intune
titleSuffix: "Azure portal"
description: Use custom configurations to create VPN profiles in Intune.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create custom VPN profiles in Microsoft Intune

## Create a custom configuration
You can use Intune custom configuration polices to create VPN profiles for:

* Devices that run Android 4 and later
* Enrolled devices that run Windows 8.1 and later
* Devices that run Windows Phone 8.1 and later
* Enrolled devices that run Windows 10 desktop 
* Devices that run Windows 10 Mobile

This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.

## To create a custom configuration policy:

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
2. On the **Device configuration** pane under the **Manage** section, choose **Profiles**.
5. On the profiles pane, choose **Create profile**.
6. On the **Create profile** pane, enter a **Name** and **Description** for the VPN profile.
7. From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings. Currently, you can choose one of the following platforms for custom device settings:
	- **Android**
	- **Android for Work**
	- **iOS** (configured using a file you exported from Apple Configurator).
	- **macOS** (configured using a file you exported from Apple Configurator).
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Custom**.
7. On the **Custom OMA-URI Settings** pane, for each URI setting you want to specify, choose **Add**, provide the requested information, then choose **OK**. Here's an example:

   ![VPN profile custom configuration dialog box](./media/Intune_Add_VPN_URI.png)

4.  After you've entered all of URI settings you need, choose **OK**, and then, on the **Create profile** pane, choose **Create**.

The profile is created and appears on the profiles list pane.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).




