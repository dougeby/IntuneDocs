---
title: IOS MAM policy settings |Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
#  IOS mobile app management policy settings
##  IOS data relocation policies
- **Prevent iTunes and iCloud backups:**
  Select Yes to disable, or No to allow backup of any information from the policy managed apps.

  **Default value = Yes**

- **Allow app to transfer data to other apps:**   Select one of the options to specify the apps that the policy managed apps can send data to:
  - *Policy managed apps*: Allow transfer to only other restricted apps
  - *All apps*: Allow transfer to any app
  - *None*: Do not allow data transfer to any app

  Additionally, if you set this option to **Policy Managed Apps** or **None**, the iOS 9 feature that allows Spotlight Search to search data within apps will be blocked.

  **Default value = Policy managed apps**

- **Allow app to receive data from other apps:**  Specify  from which apps  can transfer data to the policy managed apps:
  -  *Policy managed apps*: Allow data transfers only from other restricted apps
  -  *All apps*: Allow data transfer from any app
  -  *None*: Do not allow data transfer from any app.

  **Default value = All apps**

- **Prevent Save As:**
  Select Yes to disable the use of the Save As option in any app that uses this policy. Select No if you want to allow the use of Save As.

  **Default value = Yes**

- **Restrict cut, copy and paste with other apps:**
Specify when  cut, copy, and paste operations should be restricted. Choose from:
  -   *Blocked:* Do not allow cut, copy, and paste operations between policy managed apps.
  -   *Policy Managed Apps*: Only allow cut, copy, and paste operations between policy managed apps.
  -   *Policy Managed Apps with paste In*: Allow data cut or copied between policy managed apps. Allow data cut or copied from any app to be pasted into this app.
  - *Any App*: No restrictions for  cut, copy, and paste operations between any apps.

  **Default value =Policy managed apps with paste in**

- **Restrict web content to display in the Managed Browser:** When this setting is enabled, any links in the app will be opened in the Managed Browser.

  For devices that are not enrolled in Intune, you can restrict web links in policy-managed apps to only open in the Managed Browser app using the mobile app management policy.

  If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Default value = Yes**

- **Encrypt app data:** For apps that are associated with a [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mobile app management policy, data is encrypted at rest using device level encryption provided by the OS. When a PIN is required, the data is encrypted per the settings in the mobile app management policy. As stated in Apple documentation, [the modules used by iOS 7 are FIPS 140-2 certified](http://support.apple.com/en-us/HT202739).

  In the policy settings, you can specify PIN encryption values.  These values determine when the data is encrypted. The options are:
  - **When device is locked:** All app data associated with this policy is encrypted while the device is locked.
  -   **When device is locked (except for open files):** All app data associated with this policy is encrypted while the device is locked, except for data that in the files that are opened in the app.
  -   **After device restart:** All app data associated with this policy is encrypted when the device is restarted, until the device is unlocked for the first time.
  -   **Use device settings:** App data is encrypted based on the default settings on the device.
  When you enable this setting, the end-user is required to setup and use a PIN to access their device.  If there is not PIN setup for device access, the apps will not launch and the end-user will be prompted to set a PIN with a message -“Your company has required that you must first enable a device PIN to access this application.”

  **Default value -Encryption option is not selected.**
- **ContactSyncDisabled:**  Choose Yes to prevent contact information from synchronizing to the native address book app on the device. If you choose No, the app will save the  contact information to the native address book app on the device.

  When you do a selective wipe to remove company data, contacts synced directly from the app to the native address book are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently this is applicable only to the **Microsoft Outlook** app.

  **Default value = Yes**
##  iOS Access policy settings
- **Require simple PIN for access:**  Select Yes to require a PIN to use policy managed apps. The user is prompted to set this up the first time they run the app in a work context.

  **Default value = Yes**
- **Number of attempts before PIN reset:** Specify the number of PIN entry attempts that can be made before the user must reset the PIN.

  **There is no default value for this setting**.
- **Require fingerprint instead of PIN (iOS 8.0+):** Select Yes to require a fingerprint identity instead of a numbered PIN for app access.
On iOS devices, you can allow the user to identify themselves using fingerprint on iOS devices instead of a numbered PIN. When the end-user tries to access this app using their work account, they are prompted to provide their fingerprint identity instead of entering a PIN number.

  **Default value = Yes**
- **Require corporate credentials for access:** Select Yes to require corporate credentials instead of a PIN for app access. **If you set this to Yes, this overrides the requirements for PIN or Touch ID.** The user will be prompted to provide their corporate credentials.

  **Default value = No**
- **Block managed apps from running on jailbroken or rooted devices:** Select Yes to block apps from running on jailbroken or rooted devices. The user will continue to be able to use the apps for personal tasks, but will have to use a different device for work.

  **Default value = Yes**
- **Recheck the access requirements after (minutes)**|-   **Timeout:** Time (in minutes) before the access requirements for the app are rechecked.
  -   *Offline grace period:* If the device is offline, the time (in minutes) before the access requirements for the app are rechecked. **Default value = 30 minute timeout, and 720 minute offline grace period**
  - *Offline interval before app data is wiped (days):* You can choose to wipe the company data if a device has been offline for a certain period.  Specify the number of days a device can be offline before the company data is removed from the device. **Entering a value of  0 will turn this setting off**.

  **Default value = 90 days**|

  >[!div class="step-by-step"]
  >[Go to](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)  **Create and deploy a MAM policy**
