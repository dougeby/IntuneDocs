---
# required metadata

title: Enroll Android enterprise kiosk devices in Intune
titlesuffix: "Microsoft Intune"
description: Learn how to enroll Android enterprise kiosk devices in Intune.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
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
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up enrollment of Android enterprise kiosk devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android supports kiosk-style devices with its Corporate-Owned, Single-Use (COSU) solution set. Such devices are used for a single purpose, such as digital signage, ticket printing, or inventory management, to name just a few. Admins lock down the usage of a device for a limited set of apps and web links. It also prevents users from adding other apps or taking other actions on the device.

Intune helps you deploy apps and settings to Android kiosk devices. For specific details about Android enterprise, see [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Devices that you manage in this way are enrolled in Intune without a user account. They have no association with any end user. They aren't intended for personal use applications or apps that have a strong requirement for user-specific account data such as Outlook or Gmail.

## Device requirements

Devices must meet these requirements to be managed as an Android enterprise kiosk device:

- Android OS version 5.1 and above.
- Devices must run a distribution of Android that has Google Mobile Services (GMS) connectivity. Devices must have GMS available and must be able to connect to GMS.

## Set up Android kiosk management

To set up Android kiosk management, follow these steps:

1. To prepare to manage mobile devices, you must [set the mobile device management (MDM) authority to **Microsoft Intune**](mdm-authority-set.md) for instructions. You set this item only once, when you are first setting up Intune for mobile device management.
2. [Connect your Intune tenant account to your Android enterprise account](connect-intune-android-enterprise.md).
3. [Create an enrollment profile.](#create-an-enrollment-profile)
4. [Create a device group](#create-a-device-group).
5. [Enroll the kiosk devices](#enroll-the-kiosk-devices).

### Create an enrollment profile

You must create an enrollment profile so that you can enroll your kiosk devices. When the profile is created, it provides you with an enrollment token (random string) and a QR code. You can use either of these (depending on the Android OS version of the device) to enroll the kiosk device.

1. Go to the [Intune portal]() and choose **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**.
2. Choose **Create** and fill out the required fields.
    - **Name**: Type a name that you'll use when assigning the profile to the dynamic device group.
    - **Token expiration date**: The date when the token expires. Google enforces a maximum of 30 days.
3. Choose **Create** to save the profile.

### Create a device group

You can target apps and policies to either assigned or dynamic device groups. You can configure dynamic AAD device groups to automatically populate devices that are enrolled with a particular enrollment profile by following these steps:

1. Go to the [Intune portal]() and choose **Groups** > **All groups** > **New group**.
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
5. Choose **Add query** > **Create**.

### Replace or remove tokens

You can replace or remove tokens and QR codes.

- **Replace token**: You can generate a new token/QR code when one nears expiration by using Replace Token.
- **Revoke token**: You can immediately expire the token/QR code. From this point on, the token/QR code is no longer usable. You might use this option if you inadvertently share the token/QR code with an unauthorized party or if you complete all enrollments and no longer need the token/QR code.

Replacing or revoking a token/QR code won't have any effect on devices that are already enrolled.

1. Go to the [Intune portal]() and choose **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**.
2. Choose the profile that you want to work with.
3. Choose **Token**.
4. To replace the token, choose **Replace token**.
5. To revoke the token, choose **Revoke token**.

## Enroll the kiosk devices

After you've created the enrollment profile and dynamic device group, you can enroll your kiosk devices. How you enroll your Android devices depends on the operating system.

| Enrollment method | Minimum Android OS version supported |
| ----- | ----- |
| Near Field Communication | 5.1 |
| Token entry | 6.0 |
| QR code | 7.0 |
| Zero Touch | 8.0, on participating manufacturers |

### Enroll by using Near Field Communication (NFC)

For Android 5.1 and later devices that support NFC, you can provision your devices by creating a specially formatted NFC tag. You can use your own app or any NFC tag creator tool. For more information, see [Google's Android Management API documentation](https://developers.google.com/android/management/provision-device#nfc_method).

### Enroll by using a token

For Android 6 and later devices, you can use the token to enroll the device.

1. Turn on your factory reset device.
2. On the **Welcome** screen, select your language.
3. Connect to your **Wifi** and then choose **NEXT**.
4. Accept the Google Terms and conditions and then choose **NEXT**.
5. On the Google sign-in screen, enter **afw#setup** instead of a Gmail account, and then choose **NEXT**.
6. Choose **INSTALL** for the **Android Device Policy** app.
7. Continue installation of this policy.  Some devices may require additional terms acceptance. 
8. On the **Enroll this device** screen, allow your device to scan the QR code or choose to enter the token manually.
9. Follow the on-screen prompts to complete enrollment. 

### Enroll by using a QR code

On Android 7 and later devices, you can scan the QR code from the enrollment profile to enroll the device.

1. To launch a QR read on the Android device, tap multiple times on the first screen you see after a factory reset.
2. For Android 7 and 8 devices, you'll be prompted to install a QR reader. Android 9 and later devices already have a QR reader installed.
3. Use the QR reader to scan the enrollment profile QR code and then follow the on-screen prompts to enroll.

### Enroll by using Google Zero Touch

To use Google's Zero Touch system requires a device that supports it and is affiliated with a supplier that is part of the service.  For more information, see [Google’s Zero Touch program website](https://www.android.com/enterprise/management/zero-touch/). 


1. Create a new Configuration in the Zero Touch console.
2. Choose **Microsoft Intune** from the EMM DPC dropdown.
3. In Google’s Zero Touch console, copy/paste the following JSON into the DPC extras field. Replace the *YourEnrollmentToken* string with the enrollment token you created as part of your enrollment profile. Be sure to surround hte enrollment token with double quotes.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. Choose **Apply**.


## Next steps
- [Deploy Android kiosk apps](apps-deploy.md)
- [Add Android kiosk configuration policies](device-profiles.md)