---
# required metadata

title: Use OEMConfig on Android Enterprise devices in Microsoft Intune - Azure | Microsoft Docs
description: Use Microsoft Intune to manage and use Zebra devices running Android Enterprise with OEMConfig. See all the steps, including an overview, see the prerequisites, create the configuration profile in Intune, and see a list of the support OEMConfig apps.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/09/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority:
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Use and manage Android Enterprise Zebra devices with OEMConfig in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can use OEMConfig to add, create, and customize OEM-specific settings for Android Enterprise devices. OEMConfig is typically used to configure settings that aren't built in to Intune. Different OEMs include different settings. So the available settings depend on what the OEM includes in their OEMConfig app.

This feature applies to:  

- Android Enterprise

This article describes OEMConfig, what it does, lists the prerequisites, shows how to create a configuration profile, and lists the supported OEMConfig apps in Intune. To use Mobility Extensions (MX) on Android devices, see [Use and manage Zebra devices with Mobility Extensions](android-zebra-mx-overview.md).

## Overview

OEMConfig policies are a special type of [app configuration policy](app-configuration-policies-overview.md). OEMConfig is a standard defined by the [AppConfig community](https://www.appconfig.org/android-oemconfig/) (opens another web site) that allows OEMs (original equipment manufacturer) and EMMs (enterprise mobility management) to build and support OEM-specific features in a standardized way. Historically, EMMs, such as Intune, manually build support for OEM-specific features after they're introduced by the OEM. This approach leads to duplicated efforts and slow adoption.

With OEMConfig, an OEM creates a schema to access OEM-specific features into an app, and then puts this app on Google Play. The EMM reads the schema from the app, and exposes the schema in the EMM administrator console. The console allows Intune administrators to configure the settings in the schema.

Once the OEMConfig app is on-boarded, the OEM adds and improves features, and then updates the app in Google Play. As an administrator, you get these new features and updates (including fixes) without waiting for EMMs to include these updates.

> [!TIP]
> You can only use OEMConfig for apps that support this feature. Consult your OEM for specific details.

## Before you begin

When using OEMConfig, be aware of the following information:

- Intune exposes the OEMConfig app's schema so you can configure it. Intune doesn't validate or change the schema provided by the app. So if the schema is incorrect, or has inaccurate data, then this data is still sent to devices. Be sure your schema includes what you want and what you intend.
- Intune doesn't influence or control the content of the app schema. For example, it doesn't have any control over strings, language, the actions allowed, and so on. We recommend contacting the OEM for details and best practices for managing their devices with OEMConfig.
- At any time, OEMs update their supported features and schemas, and upload a new app to Google Play. Intune always syncs the latest version of the OEMConfig app from Google Play. Intune doesn't maintain older versions of the schema. We recommend contacting the OEM for more information.

## Prerequisites

To use OEMConfig on your devices, be sure you have the following requirements:

- An Android Enterprise 5.0 and newer device enrolled in Intune.
- An OEMConfig app built by the OEM.
- The OEMConfig app is whitelisted by Google, and uploaded to Google Play. If it's not, contact the OEM for more information.
- The Intune administrator has role-based access control (RBAC) permissions for **Mobile apps** and **DeviceConfigurations**. To manage device configurations, the OEMConfig profiles use the managed app configurations.

## Prepare the OEMConfig app

Be sure the device supports OEMConfig, and the correct OEMConfig app is installed on the device. Contact the OEM for this information.

- OEMConfig apps are specific to the OEM. For example, a Sony OEMConfig app installed on a Zebra Technologies device doesn't do anything.
- Some OEMs may ship devices with the OEMConfig app pre-installed. In other cases, you may have to manually get the app from Google Play.
- [Add Managed Google Play apps](apps-add-android-for-work.md) to Intune.

If the app isn't preinstalled, use Intune to [add and deploy the app to devices](apps-deploy.md).

## Create an OEMConfig profile

1. In the [Azure portal](https://portal.azure.com), select **All Services** > filter on **Intune** > select **Intune**.
2. Select **Device Configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

    - **Name**: Enter a descriptive name for the new profile.
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
    - **Platform**: Select **Android enterprise**.
    - **Profile type**: Select **OEMConfig**.

4. Select **Associated app**, and select an existing OEMConfig app you previously added. Be sure to choose the correct OEMConfig app for the devices you're assigning the policy.

    If you don't see any apps listed, then set up Managed Google Play, and get apps from the Managed Google Play store. [Add Managed Google Play apps to Android enterprise devices](apps-add-android-for-work.md) lists the steps.

    > [!IMPORTANT]
    > If you added an OEMConfig app and synced it to Google Play, but it's not listed as an **Associated app**, you may have to contact Intune to onboard the app. See [adding a new app](#supported-oemconfig-apps) (in this article).

5. Select the **Configuration** tab.

    A JSON editor opens with the configuration schema embedded in the app. In the editor, enter values for the different configuration settings. Since OEMConfig schemas can be large and complex, **Download JSON template** to get a sample file. Configure this sample file in an editor of your choice.

6. Select **OK** > **Add** to save your changes. The policy is created and shown in the list.

Be sure to [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

The next time the OEMConfig app on the device checks for configuration updates, the OEM-specific settings you configured are applied. Depending on the OEM, the app may be programmed to run and check for updates without any user interaction. Contact the OEM for more information.

## Supported OEMConfig apps

Compared to standard apps, OEMConfig apps expand managed configurations privileges granted by Google. Intune supports the following OEMConfig apps:

| OEM | Bundle ID |
| --- | --- |
| Samsung | com.samsung.android.knox.kpu |

To request a new OEMConfig app be on-boarded, email `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig apps must on-boarded by Intune, or added from Google Play. OEMConfig apps can't be added using **Intune** > **Client apps**.

## Next steps

- [Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
- [Use Mobility Extensions to manage Zebra devices](android-zebra-mx-overview.md).