---
# required metadata

title: Setup Intune enrollment for Android enterprise dedicated devices
titlesuffix: "Microsoft Intune"
description: Learn how to enroll Android enterprise dedicated devices in Intune.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.custom: seodec18
---

# Set up Intune enrollment of Android enterprise dedicated devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android supports corporate-owned, single-use, kiosk-style devices with its dedicated devices solution set. Such devices are used for a single purpose, such as digital signage, ticket printing, or inventory management, to name just a few. Admins lock down the usage of a device for a limited set of apps and web links. It also prevents users from adding other apps or taking other actions on the device.

Intune helps you deploy apps and settings to Android dedicated devices. For specific details about Android enterprise, see [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Devices that you manage in this way are enrolled in Intune without a user account and aren't associated with any end user. They're not intended for personal use applications or apps that have a strong requirement for user-specific account data such as Outlook or Gmail.

## Device requirements

Devices must meet these requirements to be managed as an Android enterprise dedicated device:

- Android OS version 5.1 and above.
- Devices must run a distribution of Android that has Google Mobile Services (GMS) connectivity. Devices must have GMS available and must be able to connect to GMS.

## Set up Android dedicated device management

To set up Android dedicated device management, follow these steps:

1. To prepare to manage mobile devices, you must [set the mobile device management (MDM) authority to **Microsoft Intune**](mdm-authority-set.md) for instructions. You set this item only once, when you're first setting up Intune for mobile device management.
2. [Connect your Intune tenant account to your Android enterprise account](connect-intune-android-enterprise.md).
3. [Create an enrollment profile.](#create-an-enrollment-profile)
4. [Create a device group](#create-a-device-group).
5. [Enroll the dedicated devices](#enroll-the-dedicated-devices).

### Create an enrollment profile

You must create an enrollment profile so that you can enroll your dedicated devices. When the profile is created, it provides you with an enrollment token (random string) and a QR code. Depending on the Android OS and version of the device, you can use either the token or QR code to [enroll the dedicated device](#enroll-the-dedicated-devices).

1. Go to the [Intune portal](https://portal.azure.com) and choose **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**.
2. Choose **Create** and fill out the required fields.
    - **Name**: Type a name that you'll use when assigning the profile to the dynamic device group.
    - **Token expiration date**: The date when the token expires. Google enforces a maximum of 90 days.
3. Choose **Create** to save the profile.

### Create a device group

You can target apps and policies to either assigned or dynamic device groups. You can configure dynamic AAD device groups to automatically populate devices that are enrolled with a particular enrollment profile by following these steps:

1. Go to the [Intune portal](https://portal.azure.com) and choose **Groups** > **All groups** > **New group**.
2. In the **Group** blade, fill out the required fields as follows:
    - **Group type**: Security
    - **Group name**: Type an intuitive name (like Factory 1 devices)
    - **Membership type**: Dynamic device
3. Choose **Add dynamic query**.
4. In the **Dynamic membership rules** blade, fill out the fields as follows:
    - **Add dynamic membership rule**: Simple rule
    - **Add devices where**: enrollmentProfileName
    - In the middle box, choose **Match**.
    - In the last field, enter the enrollment profile name that you created earlier.
    For more information about dynamic membership rules, see [Dynamic membership rules for groups in AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. Choose **Add query** > **Create**.

### Replace or remove tokens

You can replace or remove tokens and QR codes.

- **Replace token**: You can generate a new token/QR code when one nears expiration by using Replace Token.
- **Revoke token**: You can immediately expire the token/QR code. From this point on, the token/QR code is no longer usable. You might use this option if you:
    - accidentally share the token/QR code with an unauthorized party
    - complete all enrollments and no longer need the token/QR code

Replacing or revoking a token/QR code won't have any effect on devices that are already enrolled.

1. Go to the [Intune portal](https://portal.azure.com) and choose **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**.
2. Choose the profile that you want to work with.
3. Choose **Token**.
4. To replace the token, choose **Replace token**.
5. To revoke the token, choose **Revoke token**.

## Enroll the dedicated devices

You can now [enroll your dedicated devices](android-kiosk-fully-managed-enroll.md).

## Managing apps on Android dedicated devices

Only apps that have Assignment type [set to Required](apps-deploy.md#to-assign-an-app) can be installed on Android dedicated devices. Apps are installed from the managed Google Play store in the same manner as Android work profile devices.

Apps are automatically updated on managed devices when the app developer publishes an update to Google Play.

To remove an app from Android dedicated devices, you can do either of the following:
-   Delete the Required app deployment.
-   Create an uninstall deployment for the app.

## Next steps
- [Deploy Android apps](apps-deploy.md)
- [Add Android configuration policies](device-profiles.md)
