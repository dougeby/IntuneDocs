---
title: Android MAM policy settings |Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
# Android mobile app management policy settings in Microsoft Intune

##  Data relocation settings
- **Prevent Android backups:** Select Yes to disable, or No to allow backup of any information from the policy managed apps.

  **Default value = Yes**
- **Allow app to transfer data to other apps:** Select one of the options to specify the apps that the policy managed apps can send data to:
  -   *Policy managed apps*: Allow transfer to only other restricted apps
  -   *All apps*: Allow transfer to any app
  -   *None*: Do not allow data transfer to any app

  **Default value = Policy managed apps**
- **Allow app to receive data from other apps:** Specify  from which apps  can transfer data to the policy managed apps:
  -   *Policy managed apps*: Allow data transfers only from other restricted apps
  -   *All apps*: Allow data transfer from any app
  -   *None*: Do not allow data transfer from any app
    **Default value = All apps**
-   **Prevent Save As:** Select Yes to disable the use of the Save As option in any app that uses this policy. Select No if you want to allow the use of Save As.

  **Default value = Yes**
- **Restrict cut, copy and paste with other apps:** Specify when  cut, copy, and paste operations should be restricted. Choose from:
  -   *Blocked:* Do not allow cut, copy, and paste operations between policy managed apps.
  -   *Policy Managed Apps*: Only allow cut, copy, and paste operations between policy managed apps.
  -   *Policy Managed Apps with paste In*: Allow data cut or copied between policy managed apps. Allow data cut or copied from any app to be pasted into this app.
  -   *Any App*: No restrictions for  cut, copy, and paste operations between any apps.

    **Default value = Policy managed apps with paste in**
-   **Restrict web content to display in the Managed Browser:** When this setting is enabled, any links in the app will be opened in the Managed Browser.

  For devices that are not enrolled in Intune, you can restrict web links in policy-managed apps to only open in the Managed Browser app using the mobile app management policy.

  If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Default value = Yes**
- **Encrypt app data:** For apps that are associated with a [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mobile app management policy, encryption is provided by Microsoft. Data is encrypted synchronously during file I/O operations according to the setting in the mobile app management policy.

  Managed apps on Android use AES-128 encryption in CBC mode utilizing the platform cryptography libraries. The encryption method is not FIPS 140-2 certified. SHA-256 encryption is supported as an explicit instruction using the SigAlg parameter and will only work on devices 4.2 and above. Content on the device storage is always be encrypted.

  When you set this to Yes, the end-user is required to setup and use a PIN to access their device.  If there is not PIN setup for device access, the apps will not launch and the end-user will be prompted to set a PIN with a message -*“Your company has required that you must first enable a device PIN to access this application.”*

  **Default value = Encryption option is not selected**

- **ContactSyncDisabled:** Choose **Yes** to prevent contact information from synchronizing to the native address book app on the device. If you choose **No**, the app will save the  contact information to the native address book app on the device.<br/>When you do a selective wipe to remove company data, contacts synced directly from the app to the native address book are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently this is applicable only to the **Microsoft Outlook** app.

  **Default value = Yes**
##  Android access policy settings

- **Require simple PIN for access:** Select **Yes** to require a PIN to use policy managed apps. The user is prompted to set this up the first time they run the app in a work context.

 **Default value = Yes**
- **Number of attempts before PIN reset:** Specify the number of PIN entry attempts that can be made before the user must reset the PIN.

 **There is no default value for this setting.**
- **Require corporate credentials for access:** Select Yes to require corporate credentials instead of a PIN for app access.  If you set this to Yes, this overrides the requirements for PIN or Touch ID.  The user will be prompted to provide their corporate credentials.

  **Default value = No**
- **Block managed apps from running on jailbroken or rooted devices:** Select Yes to block apps from running on jailbroken or rooted devices. The user will continue to be able to use the apps for personal tasks, but will have to use a different device for work.

  **Default value = Yes**
- **Recheck the access requirements after (minutes)**-   **Timeout:** Time (in minutes) before the access requirements for the app are rechecked.
  -   *Offline grace period:* If the device is offline, the time (in minutes) before the access requirements for the app are rechecked.

    *Default values = 30 minute timeout, and 720 minute offline grace period*
-   **Offline interval before app data is wiped (days):** You can choose to wipe the company data if a device has been offline for a certain period.  Specify the number of days a device can be offline before the company data is removed from the device. **Tip:** Entering a value of  0 will turn this setting off.

  **Default value = 90 days**
- **Block screen capture and Android Assistant (Android 6 Marshmallow or later):** Select Yes to specify that the screen capture and **Android Assistant** capabilities of the device are blocked when using this app.

>[!div class="step-by-step"]
[<<Create and Deploy a MAM policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)  
[Monitor compliance>>](monitor-mobile-app-management-policies-with-microsoft-intune.md)
