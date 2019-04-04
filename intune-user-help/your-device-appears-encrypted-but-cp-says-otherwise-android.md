---
# required metadata

title: Your Android device seems to be encrypted | Microsoft Docs
description: 
keywords:
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
 - User help

# optional metadata

ROBOTS:  
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
---


# Your Android device seems to be encrypted, but Company Portal says otherwise

When you encrypt a device, you are encoding the information on it using a secret key that is known only to you. This prevents unauthorized people from accessing it. Many organizations require their users to encrypt their Android devices before they can access company files, email, or data.

## Common issues

Newer versions of Android, particularly starting with v7.0, require a startup passcode to make sure that your device is fully encrypted. Different device manufacturers have varying descriptions and locations for the startup passcode. Most of the time, this setting is referred to as "Secure Startup." 

## Solutions

### Add a startup PIN

Certain Android devices require you to create a startup PIN to make sure that your device is secure. There are many versions of Android from many different manufacturers. You can try to fix this issue by finding a location in your settings app to enable this option. For example, on the Samsung Galaxy S7, you enable Secure Startup by going to **Settings** > **Lock Screen and Security** > **Secure Startup**.  

### Encrypt the entire device

Some devices will give you a choice between encrypting the entire device or just the used space. Choose the option to encrypt the entire device rather than "only used space." If you have already encrypted only the used space:

1. [Remove this device from the Company Portal](unenroll-your-device-from-intune-android.md)
2. Decrypt the used space
3. Encrypt the entire device
4. Re-enroll the device

### Downgrade your version of Android

If your device offers you the option to downgrade to Android 6.0+, then do so. There is a risk of data loss if you should try to downgrade your device. Otherwise, we recommend that you contact your company support to resolve this issue. You can get contact information for your company support at the [Company Portal website](https://go.microsoft.com/fwlink/?linkid=2010980) for contact information.

## Specific manufacturer issues

Some Android devices on version 7.0+ encrypt data in ways that are inconsistent with certain Android platform standards. These devices may appear encrypted even when they are brand new. Intune recognizes that these devices' encryption methods put the device's information at risk. This risk primarily stems from malicious users who have physical access to the device.

> [!Note]
> Microsoft works with manufacturers to address any issues we find while testing, or that users report to us. We update this article whenever new information is available. 

## Known devices

### Known devices that can be updated to fix this issue

If you haven't updated your device to the most recent version of Android, go to your device's **Settings** app and select **Update**. These devices might appear as non compliant until you update:  

- Huawei Honor 8
- Huawei P9

### Known devices that currently cannot be updated to fix this issue
The following devices will always appear encrypted and can't be used to access company resources. To access company resources, you must use a different device.  

- Huawei Mate 8
- OPPO devices
- Vivo devices
- Xiaomi Mi smartphones
