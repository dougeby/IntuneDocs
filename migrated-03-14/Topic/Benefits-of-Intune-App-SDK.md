---
title: Benefits of Intune App SDK
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
author: Msmbaldwin
---
# Benefits of Intune App SDK
The Intune App SDK is available for both the iOS and Android platform, and enables mobile app management features with Microsoft Intune. In addition, we strive to reduce the amount of code changes required of the developer. You will find that you can enable most of the SDK features without changing your app’s behavior. For enhanced end user and IT administrator experience, you can utilize our APIs to customize your app behavior for features that require your app participation. 
Once you’ve enabled your app, IT administrators can deploy policies to Intune managed apps and take advantage of these features to protect their corporate data.

## Regular Features

### Control users’ ability to move corporate documents
IT administrators can control file relocation of corporate documents in Intune managed apps. For instance, they can deploy a policy that disables file backup apps from backing up corporate data to the cloud.

### Configure clipboard restrictions
IT administrators can configure the clipboard behavior in Intune managed apps. For instance, they can deploy a policy so that end users are unable to use the clipboard to cut/copy from an Intune-managed app and paste into a non-managed app.

### Configure screen capture restrictions
IT administrators can prevent users from capturing the screen if an Intune-managed app is displayed. Applying this restriction prevents the capture and release of confidential corporate content. This feature is only available for android devices.

### Enforce encryption on saved data
IT administrators can enforce a policy that ensures that data saved to the device by the app is encrypted.

### Remotely wipe corporate data
IT administrators can remotely wipe corporate data from an Intune-managed app when the device is unenrolled from Microsoft Intune. This feature is identity-based and will delete only the files that relate to the corporate identity of the end user. To do that, the feature requires the app’s participation. The app can specify the identity for which the wipe should occur based on user settings. In the absence of these specified user settings from the app, the default behavior is to wipe the application directory and notify the end user that company resource access has been removed.

### Enforce the use of a managed browser
IT administrators can enforce the use of a managed browser when opening links from within Intune-managed apps. Using the Microsoft Intune managed browser helps to ensure that links that appear in emails (which are in an Intune-managed mail client) are kept within the domain of Intune managed apps.

### Enforce a PIN policy
IT administrators can enforce a PIN policy when an Intune-managed app is started. This policy helps to ensure that the end users who enrolled their devices with Microsoft Intune are the same individuals who are starting the apps. When end users configure their PIN, Intune App SDK uses Azure Active Directory to verify the credentials of end users against the device enrollment credentials

### Require users to enter credentials before they can start apps
IT administrators can require users to enter their credentials before users can start an Intune-managed app. Intune App SDK uses Azure Active Directory to provide a single sign-on experience, where the credentials, once entered, are reused for subsequent logins. We also support authentication of identity management solutions [federated with Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx).

### Check device health and compliance
IT administrators can a check the health of the device and its compliance with corporate policies before end users access Intune-managed apps. On the iOS platform, this policy checks if the device has been jailbroken. On the Android platform, this policy checks if the device has been rooted.

## Preview Features
The Microsoft Intune App SDK includes several features that are in "preview". You can begin integrating with preview APIs, but for testing purposes only. Note that these previews add to existing scenarios rather than replace existing scenarios.

### Microsoft Intune App SDK multi-identity Support
Multi-identity support is a feature that enables coexistence of policy-managed (corporate) and unmanaged (personal) accounts in a single app.

### Example of a multi-identity scenario
Many users configure both corporate and personal email accounts in the Outlook app for iOS and Android. When a user is accessing data in their corporate account, the IT administrator must be confident that MAM policy management will be applied. However, when a user is accessing a personal email account, that data should be outside of the IT administrator's control. Microsoft Intune achieves this by targeting the management policy to the corporate account only in the application. This multi-identity feature helps solve the data protection problem that organizations are facing with devices and apps that support both personal and work accounts.

### How to support multi-identity
Preview APIs allow you to specify a User Principal Name (UPN) with specific data operations such as clipboard operations and file operations. The Microsoft Intune App SDK uses the UPN to match the call made to the UPN that was used to enroll the device with the Microsoft Intune service. If the UPNs match, the call is treated as a "corporate data" call and the data is protected; if the UPNs do not match, the call is treated as a "personal data" call, and the data is not protected.

### App management without device enrollment
Many users with personal devices wish to see and use corporate data without enrolling their personal device with a Mobile Device Management (MDM) product. Since MDM enrollment requires global control of the device, users hesitate to give that global control to their own personal device to their company.

App management without device enrollment allows the Microsoft Intune service to deploy MAM policy to an app directly, without relying on an MDM channel to deploy the policy. Since no MDM channel is needed, MDM enrollment is not needed.

