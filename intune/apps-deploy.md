---
# required metadata

title: Assign apps to groups in Microsoft Intune
titlesuffix:
description: Learn how to assign an Intune app to groups of users or devices using Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Assign apps to groups with Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

After you've [added an app](apps-add.md) to Microsoft Intune, you can assign the app to users and devices. It is important to note that you can assign an app to a device whether or not the device is managed by Intune.

> [!NOTE]
> The Available deployment intent is not supported for device groups, only user groups are supported.

The following table lists the various options for assigning apps to users and devices:

|   | Devices enrolled with Intune | Devices not enrolled with Intune |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Assign to users | Yes | Yes |
| Assign to devices | Yes | No |
| Assign wrapped apps or apps that incorporate the Intune SDK (for app protection policies) | Yes | Yes |
| Assign apps as Available | Yes | Yes |
| Assign apps as Required | Yes | No |
| Uninstall apps | Yes | No |
| Receive app updates from Intune | Yes | No |
| End users install available apps from the Company Portal app | Yes | No |
| End users install available apps from the web-based Company Portal | Yes | Yes |

> [!NOTE]
> Currently, you can assign iOS and Android apps (line-of-business and store-purchased apps) to devices that aren't enrolled with Intune.
>
> To receive app updates on devices that aren't enrolled with Intune, device users must go to their organization's Company Portal and manually install app updates.

## Assign an app

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. In the **Intune** menu, select **Client apps**.
4. In the **Manage** section of the menu, select **Apps**.
5. In the **Apps** pane, select the app you want to assign.
6. In the **Manage** section of the menu, select **Assignments**.
7. Select **Add Group** to open the **Add group** pane that is related to the app.
8. For the specific app, select an **assignment type**:
   - **Available for enrolled devices**: Assign the app to groups of users who can install the app from the Company Portal app or website.
   - **Available with or without enrollment**: Assign this app to groups of users whose devices are not enrolled with Intune. Users must be assigned an Intune license, see [Intune Licenses](licenses.md).
   - **Required**: The app is installed on devices in the selected groups. Some platforms may have additional prompts for the end user to acknowledge before app installation begins.
   - **Uninstall**: The app is uninstalled from devices in the selected groups if Intune has previously installed the application onto the device via an "Available for enrolled devices" or "Required" assignment using the same deployment. Web links cannot be removed after deployment.

     > [!NOTE]
     > **For iOS apps only**: If you have created an iOS VPN profile that contains per-app VPN settings, you can select the VPN profile under **VPN**. When the app is run, the VPN connection is opened. For more information, see [VPN settings for iOS devices](vpn-settings-ios.md).
     >
     > **For Android apps only**: If you deploy an Android app as **Available with or without enrollment**, reporting status will only be available on enrolled devices.

9. To select the groups of users that are affected by this app assignment, select **Included Groups**.
10. After you have selected one or more groups to include, select **Select**.
11. In the **Assign** pane, select **OK** to complete the included groups selection.
12. If you want to exclude any groups of users from being affected by this app assignment, select **Exclude Groups**.
13. If you have chosen to exclude any groups, in **Select groups**, select **Select**.
14. In the **Add group** pane, select **OK**.
15. In the app **Assignments** pane, select **Save**.

The app is now assigned to the groups that you selected. For more information about including and excluding app assignments, see [Include and exclude app assignments](apps-inc-exl-assignments.md).

## How conflicts between app intents are resolved

Sometimes, the same app is assigned to multiple groups but with different intents. The information in the following table can help you understand the resulting intent when this occurs:

| Group 1 intent | Group 2 intent | Resulting intent |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|User Required|User Available|Required and Available|
|User Required|User Not Available|Required|
|User Required|User Uninstall|Required|
|User Available|User Not Available|Not Available|
|User Available|User Uninstall|Uninstall|
|User Not Available|User Uninstall|Uninstall
|User Required|Device Required|Both exist, Intune treats Required
|User Required|Device Uninstall|Both exist, Intune resolves Required
|User Available|Device Required|Both exist, Intune resolves Required (Required and Available)
|User Available|Device Uninstall|Both exist, Intune resolves Available.<br><br>App shows up in the Company Portal.<br><br>If the app is already installed (as a required app with previous intent), the app is uninstalled.<br><br>If the user selects **Install from the Company Portal**, the app is installed, and the uninstall intent is not honored.|
|User Not Available|Device Required|Required|
|User Not Available|Device Uninstall|Uninstall|
|User Uninstall|Device Required|Both exist, Intune resolves Required|
|User Uninstall|Device Uninstall|Both exist, Intune resolves Uninstall|
|Device Required|Device Uninstall|Required|
|User Required and Available|User Available|Required and Available|
|User Required and Available|User Uninstall|Required and Available|
|User Required and Available|User Not Available|Required and Available|
|User Required and Available|Device Required|Both exist, Required and Available
|User Required and Available|Device Not Available|Required and Available|
|User Required and Available|Device Uninstall|Both exist, Intune resolves Required (Required and Available)
|User Not Available|Device Not Available|Not Available|
|User Available|Device Not Available|Available|
|User Required|Device Not Available|Required|
|User Available without enrollment|User Required and Available|Required and Available
|User Available without enrollment|User Required|Required
|User Available without enrollment|User Not Available|Not Available
|User Available without enrollment|User Available|Available|
|User Available without enrollment|Device Required|Required and Available without enrollment|
|User Available without enrollment|Device Not Available|Available without enrollment|
|User Available without enrollment|Device Uninstall|Uninstall and Available without enrollment.<br><br>If the user didn’t install the app from the Company Portal, the uninstall is honored.<br><br>If the user installs the app from the Company Portal, the install is prioritized over the uninstall.|

> [!NOTE]
> For managed iOS store apps only, when you add these apps to Microsoft Intune and assign them as **Required**, the apps are automatically created with both **Required** and **Available** intents.<br><br>
> iOS Store apps (not iOS VPP apps) that are targeted with required intent will be enforced on the device at the time of the device check-in and will also show in the Company Portal app.

## Managed Google Play app deployment to unmanaged devices
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you can use Managed Google Play to deploy store apps and line-of-business (LOB) apps to users. Managed Google Play apps targeted as **Available with or without enrollment** will appear in the Play Store app on the end user's device, and not in the Company Portal app. End user will browse and install apps deployed in this manner from the Play app. Because the apps are being installed from managed Google Play, the end user will not need to alter their device settings to allow app installation from unknown sources, which means the devices will be more secure. If the app developer publishes a new version of an app to Play that was installed on a user's device, the app will be automatically updated by Play. 

Steps to assign a Managed Google Play app to unmanaged devices:

1. Connect your Intune tenant to managed Google Play. If you have already done this in order to manage Android Enterprise work profile, dedicated, or fully managed devices, you do not need to do it again.
2. Add apps from managed Google Play to your Intune console.
3. Target managed Google Play apps as **Available with or without enrollment** to the desired user group. **Required** and **Uninstall** app targeting are not supported for non-enrolled devices.
4. Assign an App Protection Policy to the user group.
5. The next time the end user opens the Company Portal app, they will see a message indicating that there are apps available for them in the Play Store app.  The user can tap this notification to be brought directly to the Play app to see corporate apps, or they can navigate to the Play Store app separately.
6. The end user can expand the context menu within the Play Store app and switch between their personal Google account (where they see their personal apps), and their work account (where they will see store and LOB apps targeted to them). End users install the apps by tapping Install in the Play Store app.

When an APP selective wipe is issued in the Intune console, the work account will be automatically removed from the Play Store app and the end user will from that point no longer see work apps in the Play Store app catalog. When the work account is removed from a device, apps installed from the Play Store will remain installed on the device and will not uninstall. 

## Next steps

To learn more about monitoring app assignments, see [How to monitor apps](apps-monitor.md).
