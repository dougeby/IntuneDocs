---
# required metadata

title: Overview of the Microsoft Intune App SDK | Microsoft Docs
description: The Intune App SDK is available for both the iOS and Android platforms, and enables mobile app management features with Microsoft Intune. 
keywords:
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oydang
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Overview of the Microsoft Intune App SDK
The Intune App SDK is available for both the iOS and Android platforms, and enables mobile app management features with Microsoft Intune. In addition, it strives to reduce the amount of code changes that the developer has to make.

You will find that you can enable most of the SDK features without changing your app’s behavior. For enhanced end-user and IT administrator experiences, you can utilize our APIs to customize your app behavior for features that require your app participation.

Once you’ve enabled your app, IT administrators can deploy policies to Intune managed apps and take advantage of these features to protect their corporate data.

## Features
### Control users’ ability to move corporate documents
IT administrators can control file relocation of corporate documents in Intune managed apps. For example, they can deploy a policy that disables file backup apps from backing up corporate data to the cloud.  

### Configure clipboard restrictions
IT administrators can configure the clipboard behavior in Intune managed apps. For example, they can deploy a policy so that end users can't use the clipboard to cut or copy from an Intune-managed app and paste into a non-managed app.

### Enforce encryption on saved data
IT administrators can enforce a policy that ensures that data that is saved to the device by the app is encrypted.

### Remotely wipe corporate data
IT administrators can remotely wipe corporate data from an Intune-managed app when the device is unenrolled from Microsoft Intune. This feature is identity-based and only deletes files that relate to the corporate identity of the end user. To do that, the feature requires the app’s participation. The app can specify the identity for which the wipe should occur based on user settings. In the absence of these specified user settings from the app, the default behavior is to wipe the application directory and notify the end user that company resource access has been removed.

### Enforce the use of a managed browser
IT administrators can enforce the use of a managed browser when users open links from within Intune-managed apps. When end users use the Microsoft Intune managed browser, it helps to ensure that links that appear in emails in an Intune-managed email client are kept within the domain of Intune managed apps.

### Enforce a PIN policy
IT administrators can enforce a PIN policy when an Intune-managed app is started. This policy helps to ensure that the end users who enrolled their devices with Microsoft Intune are the same individuals who are starting the apps. When end users configure their PIN, the Intune App SDK uses Azure Active Directory to verify their credentials against the device enrollment credentials.

### Require users to enter credentials before they can start apps
IT administrators can require end users to enter their credentials before they start an Intune-managed app. The Intune App SDK uses Azure Active Directory to provide a single sign-in experience. This means that the credentials, once entered, are reused for subsequent sign-ins. The SDK also supports the authentication of identity management solutions that are [federated with Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

### Check device health and compliance
IT administrators can check the health of the device and its compliance with corporate policies before end users can access Intune-managed apps. On the iOS platform, this policy checks if the device has been jailbroken. On the Android platform, this policy checks if the device has been rooted.  
