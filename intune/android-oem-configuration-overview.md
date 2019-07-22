---
# required metadata

title: Use OEMConfig on Android Enterprise devices in Microsoft Intune - Azure | Microsoft Docs
description: Use Microsoft Intune to manage and use devices running Android Enterprise with OEMConfig. See all the steps, including an overview, see the prerequisites, create the configuration profile in Intune, and see a list of supported OEMConfig apps.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2019
ms.topic: conceptual
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

# Use and manage Android Enterprise devices with OEMConfig in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can use OEMConfig to add, create, and customize OEM-specific settings for Android Enterprise devices. OEMConfig is typically used to configure settings that aren't built in to Intune. Different OEMs include different settings. So the available settings depend on what the OEM includes in their OEMConfig app.

This feature applies to:  

- Android Enterprise

This article describes OEMConfig, what it does, lists the prerequisites, shows how to create a configuration profile, and lists the supported OEMConfig apps in Intune.

## Overview

OEMConfig policies are a special type of device configuration policy very similar to [app configuration policy](app-configuration-policies-overview.md). OEMConfig is a standard defined by the [AppConfig community](https://www.appconfig.org/android-oemconfig/) (opens another web site) that allows OEMs (original equipment manufacturers) and EMMs (enterprise mobility management) to build and support OEM-specific features in a standardized way. Historically, EMMs, such as Intune, manually build support for OEM-specific features after they're introduced by the OEM. This approach leads to duplicated efforts and slow adoption.

With OEMConfig, an OEM creates a schema that defines OEM-specific management features. The OEM embeds the schema into an app, and then puts this app on Google Play. The EMM reads the schema from the app, and exposes the schema in the EMM administrator console. The console allows Intune administrators to configure the settings in the schema.

When the OEMConfig app is installed on a device, it can use the settings configured in the EMM administrator console to manage the device. Settings on the device are executed by the OEMConfig app, instead of an MDM agent built by the EMM.

When the OEM adds and improves management features, the OEM also updates the app in Google Play. As an administrator, you get these new features and updates (including fixes) without waiting for EMMs to include these updates.

> [!TIP]
> You can only use OEMConfig with devices that support this feature and have a corresponding OEMConfig app. Consult your OEM for specific details.

## Before you begin

When using OEMConfig, be aware of the following information:

- Intune exposes the OEMConfig app's schema so you can configure it. Intune doesn't validate or change the schema provided by the app. So if the schema is incorrect, or has inaccurate data, then this data is still sent to devices. If you find a problem that originates in the schema, contact the OEM for guidance.
- Intune doesn't influence or control the content of the app schema. For example, Intune doesn't have any control over strings, language, the actions allowed, and so on. We recommend contacting the OEM for details and best practices for managing their devices with OEMConfig.
- At any time, OEMs can update their supported features and schemas, and upload a new app to Google Play. Intune always syncs the latest version of the OEMConfig app from Google Play. Intune doesn't maintain older versions of the schema or the app. If you run into version conflicts, we recommend contacting the OEM for more information.
- You should only assign one OEMConfig profile to a device. If multiple profiles are assigned to the same device, you may see inconsistent behavior. The OEMConfig model only supports a single policy per device.

## Prerequisites

To use OEMConfig on your devices, be sure you have the following requirements:

- An Android Enterprise device enrolled in Intune.
- An OEMConfig app built by the OEM, and uploaded to Google Play. If it's not on Google Play, contact the OEM for more information.
- The Intune administrator has role-based access control (RBAC) permissions for **Mobile apps** and **DeviceConfigurations**. This is because OEMConfig profiles make use of managed app configurations to manage device configurations.

## Prepare the OEMConfig app

Be sure the device supports OEMConfig, that the correct OEMConfig app has been added to Intune, and that the app is installed on the device. Contact the OEM for this information.

> [!TIP] 
> OEMConfig apps are specific to the OEM. For example, a Sony OEMConfig app installed on a Zebra Technologies device doesn't do anything.

1. Get the OEMConfig app from the Managed Google Play Store. [Add Managed Google Play apps to Android enterprise devices](apps-add-android-for-work.md) lists the steps.
2. Some OEMs may ship devices with the OEMConfig app pre-installed. If the app isn't preinstalled, use Intune to [add and deploy the app to devices](apps-deploy.md).

## Create an OEMConfig profile

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Select **Device Configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

    - **Name**: Enter a descriptive name for the new profile.
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
    - **Platform**: Select **Android enterprise**.
    - **Profile type**: Select **OEMConfig**.

4. Select **Associated app**, and select an existing OEMConfig app you previously added. Be sure to choose the correct OEMConfig app for the devices you're assigning the policy to.

    If you don't see any apps listed, then set up Managed Google Play, and get apps from the Managed Google Play store. [Add Managed Google Play apps to Android enterprise devices](apps-add-android-for-work.md) lists the steps.

    > [!IMPORTANT]
    > If you added an OEMConfig app and synced it to Google Play, but it's not listed as an **Associated app**, you may have to contact Intune to onboard the app. See [adding a new app](#supported-oemconfig-apps) (in this article).

5. Select the **Configuration** tab.

    A JSON editor opens with a template for the configuration schema embedded in the app. In the editor, customize the template with values for the different configuration settings. 
    
    Since OEMConfig schemas can be large and complex, you can use the **Download JSON template** button to get the template as a file. Configure this template file in an editor of your choice, then copy the contents into the Intune administrative console.

6. Select **OK** > **Add** to save your changes. The policy is created and shown in the list.

Be sure to [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
    
 > [!NOTE]
 > Assign one profile to each device. The OEMConfig model only supports one policy per device.

The next time the device checks for configuration updates, the OEM-specific settings you configured are applied to the OEMConfig app.

> [!NOTE]
> The OEMConfig standard doesn't currently include status reporting, so profiles will show a status of **Pending** by default.

## Supported OEMConfig apps

Compared to standard apps, OEMConfig apps expand the managed configurations privileges granted by Google to support more complex schemas. Intune currently supports the following OEMConfig apps:

-----------------

| OEM | Bundle ID | OEM Documentation (if available) |
| --- | --- | ---|
| Samsung | com.samsung.android.knox.kpu | [Knox Service Plugin Admin Guide](https://docs.samsungknox.com/knox-service-plugin/admin-guide/welcome.htm)

-----------------

To request a new OEMConfig app be on-boarded, email `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig apps must on-boarded by Intune before they can be configured with OEMConfig profiles.

## Next steps

- [Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
