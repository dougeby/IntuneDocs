---
# required metadata

title: How to deploy apps | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Deploy apps in Microsoft Intune

Use the information in this topic to help you deploy Microsoft Intune apps.


## Deploy an app
In this procedure, you'll deploy the app to selected devices or users.

### To deploy an app

1. In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Apps** &gt; **Apps** to view the list of apps you manage.

2.  Select the app you want to deploy, and then click **Manage Deployment**.

3.  In the *&lt;app name&gt;* dialog box, first, on the **Select Groups** page, choose the user or device groups to which you want to deploy the app.

4.  On the **Deployment Action** page, configure the following:

	- **Approval** - Choose whether the deployment is:
		- **Required** (mandatory install)
		- **Available** (users install from the company portal on demand)
		- **Not Applicable** (the app is not installed or shown in the company portal)
		- **Uninstall** (the app will be uninstalled from targeted devices).
	- **Deadline** - For required installations, choose how soon the app will be deployed. You can choose from the predefined values, or select **Custom** to configure your own deadline.

5. If the app you are deploying can be configured by a mobile application management policy, the **Mobile App Management** page is displayed. On this page, choose the mobile application management policy you want to associate with this app.

	[See which Microsoft apps are compatible with mobile application management policies.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. If the app you are deploying is compatible with Intune VPN profiles, the **VPN Profile** page is displayed. On this page, you can choose to associate iOS apps with a VPN profile you have deployed. The VPN connection will be automatically opened when the app is launched. To make a VPN profile available, it must have the **Per-app VPN** profile setting enabled.
 For information about how to configure VPN profiles, including support for associating profiles with apps, see [Help users connect to their work using VPN profiles with Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Example

In this example, you deployed the app as **Available** to an iOS device.
The app will be displayed in the company portal on users device from where they can install the app. For example, in this screenshot, the Bing for iOS app was deployed using the **External Link** installation type, with a custom icon, and the option **Display this as a featured app and highlight it in the company portal** was selected.
	![iOS available app](./media/available-install-on-iOS.png)

If you deployed the app as **Required** to an iOS device, the user will get a notification that an app is ready to install. For example, in this screenshot, the Work Folders for iOS app was deployed using the **Managed iOS app from the app store** installation type.
	![iOS required app](./media/iOS-Required-install.PNG)

## Next steps

After you deploy an app, you'll want to monitor it's progress. For more information, see [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).
