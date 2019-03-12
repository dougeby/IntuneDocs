---
# required metadata

title: Use Zebra MX on Android devices in Microsoft Intune - Azure | Microsoft Docs
description: Use Microsoft Intune to manage and use Zebra devices running Android with Mobility Extensions (MX). See all the steps, including install the Company Portal app, sideload the app, assign device administrator role, create a StageNow profile, and more.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/12/2019
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

# Use and manage Zebra devices with Mobility Extensions in Microsoft Intune

How-to guides > Configure devices > Manage Zebra devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can use **Mobility Extensions (MX)** to manage Android devices manufactured by Zebra Technologies, also known as "Zebra devices". You can use MX to add, create, and customize settings for Android Zebra devices. 

This feature applies to:

- Android

Your company may use Zebra devices for retail, on the factory floor, and more. For example, you're a retailer and your environment includes thousands of Zebra mobile devices used by sales associates. As part of your mobile device management (MDM) solution, Intune can help manage these devices.

Intune includes a rich set of features to manage apps and configure device settings. Using Intune, you can "enroll" Zebra devices to manages apps, and deploy your line-of-business apps to the devices. "Device configuration profiles" let you add or disable settings and features, including creating MX profiles to add Zebra-specific settings.

This article shows you how to use Mobility Extensions (MX) on Zebra devices in Microsoft Intune.

## Before you begin

- Be sure to check Zebra's [full MX feature matrix](http://techdocs.zebra.com/mx/compatibility) to confirm the profiles you create are compatible with the device's MX version, OS version, and model.
- TC20/25 devices only support some of the MX features. TC20/25 devices don't support all of the available MX features.

## Step 1: Install the latest Company Portal app

On the device, go to the Google Play store, and download and install the Intune Company Portal app from Microsoft. When installed from Google Play, the Company Portal app gets updates and fixes automatically.

If Google Play isn't available, download the [Microsoft Intune Company Portal for Android](https://www.microsoft.com/download/details.aspx?id=49140) (opens another Microsoft website), and [sideload it](#sideload-the-company-portal-app). When installed this way, the app doesn't receive updates or fixes automatically. Update and patch the app manually.

### Sideload the Company Portal app

Sideload is when you don't use Google Play to download an app. To sideload the Company Portal app, use StageNow. The following steps provide an overview. For specific details, see Zebra's documentation. [Enroll in an MDM using StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (opens Zebra's web site) may be a good resource.

1. In StageNow, create a profile for **Enroll in an MDM**.
2. In **Deployment**, choose to download the MDM agent file.
3. Set the **Support App** and **Download Configuration** steps to **No**.
4. In **Download MDM**, select **Transfer/Copy File**. Add the source and destination of the Company Portal Android package (APK).
5. In **Launch MDM**, leave the default values as-is. Add the following details:

    - **Package Name**: `com.microsoft.windowsintune.companyportal`
    - **Class Name**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

> [!TIP]
> For more information on StageNow, and what it does, see [StageNow Android device staging](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (opens Zebra's web site).

## Step 2: Confirm the Company Portal app has device administrator role

Most Zebra devices include a UI to activate the Device Administrator role. If a UI isn't available, use StageNow to manually grant Device Administrator permissions to the Company Portal app. Grant the Device Administrator before you deploy the StageNow app to the devices.

[Set battery swap mode as device administrator](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (opens Zebra's website) lists the steps. When prompted, be sure to enter the following information:

- **Device Admin Package Name**: Enter `com.microsoft.windowsintune.companyportal`
- **Device Admin Class Name**: Enter `com.microsoft.omadm.client.PolicyManagerReceiver`

## Step 3: Enroll the device in to Intune

[Enroll Android devices](android-enroll.md) lists the steps. If you have many Zebra devices, you may want to use a [device enrollment manager account](device-enrollment-manager-enroll.md).

## Step 4: Create a profile in StageNow

When you [create the profile in StageNow](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (opens Zebra's web site), the last step generates an XML file. Select **Export to MDM**, and save this file. You need it in a later step.

> [!TIP]
> Once you have this file, it's recommended to test the profile before you deploy it to devices in your organization. To test, generate a barcode or sound file with StageNow on your computer. Then, consume the barcode or sound file with the StageNow app on the device. [Use StageNow logs on Zebra devices running Android in Intune](android-zebra-mx-logs-troubleshoot.md) has information on the StageNow logs.

After you test the file, the next step is to deploy the profile to devices using Intune.

> [!NOTE]
> Deploy one profile to each device. If there are multiple StageNow profiles you want to deploy on the devices, then export the StageNow profiles, and combine the settings into a single XML file. For example, you don’t want two settings that configure the same property in the same XML file. The goal is to prevent conflicts between settings before you add the StageNow file to the Intune profile.

## Step 5: Create a profile in Intune

In Intune, create a device configuration profile:

1. In the [Azure portal](https://portal.azure.com), select **All Services** > filter on **Intune** > select **Intune**.
2. Select **Device Configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

    - **Name**: Enter a descriptive name for the new profile.
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
    - **Platform**: Select **Android**.
    - **Profile type**: Select **MX profile (Zebra only)**.

4. In **MX profile in .xml format**, add the XML profile file you exported from StageNow (#step-4-create-a-profile-in-stagenow) (in this article).
5. Select **OK** > **Create** to save your changes. The policy is created and shown in the list.

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

The next time the device checks for configuration updates, the MX profile is deployed to the device. Devices sync with Intune when devices enroll, and then  approximately every 8 hours. You can also force a sync. On the device, open the **Company Portal app** > **Settings** > **Sync**.

> [!TIP]
> - For security reasons, you won’t see the profile XML text after you save it. The text is encrypted, and you only see asterisks (`****`). For your reference, it's recommended to save copies of the MX profiles before you add them to Intune.
> 
> - To update a profile after it's assigned to Zebra devices, create an updated StageNow XML file, change the existing Intune profile, and add the new StageNow XML file. This new files overwrites the old StageNow policy.

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

[Use StageNow logs to troubleshoot Zebra devices](android-zebra-mx-logs-troubleshoot.md).