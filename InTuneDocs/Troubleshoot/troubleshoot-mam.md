---
# required metadata

title: Troubleshoot mobile application management | Microsoft Intune
description: This topic describes some troubleshooting tips for conditional access deployments.
keywords:
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.author: oldang
ms.date: 09/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: joglocke
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot mobile application management

If you are having problems with Intune mobile application management, start here. This topic contains some common problems and questions you might have and provides solutions and answers.



## Frequently asked questions (FAQ)

### MAM Basics


1. **What is MAM?** Intune mobile application management (MAM) refers to the set of features that enable IT administrators to manage corporate mobile applications. The features include app deployment, app protection policies, and app administration.

2. **What are the benefits of MAM?** MAM protects an organization's data within an application. With MAM-WE, a work or school-related app that contains sensitive data can be managed on almost any device, including personal devices in bring-your-own-device (BYOD) scenarios. Many productivity apps, such as the Microsoft Office apps, are able to be managed by Intune MAM. See the official list of [Intune-enlightened apps](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) available for public use.

3. **What device configurations does MAM support?** Intune MAM supports two configurations:
  1. **Intune MDM + MAM**: This is the first configuration supported by MAM when it first launched. IT administrators can only manage apps using MAM and app protection policies on devices that are enrolled with Intune mobile device management (MDM). To manage apps using MDM + MAM, customers should use the Intune standalone console at http://manage.microsoft.com.

  2. **MAM without device enrollment**: MAM without device enrollment, or MAM-WE, allows IT administrators to manage apps using MAM and app protection policies on devices not enrolled with Intune MDM. This means apps can be managed by Intune on devices enrolled with third-party EMM providers. To manage apps using MAM-WE, customers should use the Intune console in the Azure portal at http://portal.azure.com.

### MAM apps

1. **Which apps can be managed by MAM?** Any app that has been enlightened by the [Intune App SDK](../develop/intune-app-sdk) or wrapped by the [Intune App Wrapping Tool](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) can be managed by Intune MAM. See the official list of [Intune-enlightened apps](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) available for public use.

2. **How does MAM work with apps?** The purpose of MAM is to protect an organization's data at the application level. IT administrators achieve this by managing apps using app protection policies that ensure end-users interact with their organization's data within the app in a safe and protected way, designated by their IT administrator.

3. **What are the baseline requirements to use an Intune managed app?**
  1. The end-user must have an Azure Active Directory (AAD) account. Read this [article](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) to learn how to create Intune users in Azure Active Directory.

  2. The end-user must have a license for Microsoft Intune assigned to their Azure Active Directory account. Click [here](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4) to learn how to assign Intune licenses to end-users.

  3. The end-user must belong to a security group that is targeted by an app protection policy. The same app protection policy must target the specific app being used. App protection policies can be created and deployed in the Intune console in the [Azure portal](http://portal.azure.com). Security groups can currently be created in the [Office portal](http://portal.office.com).

  4. The end-user must sign into the app using his or her AAD account.

4. **What are the additional requirements to use [Outlook mobile](https://www.microsoft.com/en-us/outlook-com/mobile/)?**

  1. The end-user must have the Outlook mobile app installed to their device.

  2. The end-user must have an [Office 365 Exchange Online](https://products.office.com/en-us/exchange/exchange-online) mailbox and license linked to their Azure Active Directory account.

  >[!NOTE]
  > The Outlook mobile apps currently do not support Microsoft Exchange On-Premises or Exchange in Office 365 Dedicated.

5. **What are the additional requirements to use [Word, Excel, & PowerPoint](https://products.office.com/business/office)?**

  1. The end-user must have a license for [Office 365 Business or Enterprise](https://products.office.com/business/office) linked to their Azure Active Directory account. The subscription must include a cloud storage account with [OneDrive for Business](https://onedrive.live.com/about/business/). Office 365 licenses can be assigned in the [Office portal](http://portal.office.com) following these [instructions](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&rs=en-US&ad=US).

  2. The end-user must have the [OneDrive](https://onedrive.live.com/about/) app installed to their device and sign in with their AAD account.

  3. The OneDrive app must be targeted by the app protection policy deployed to the end-user.

8. **Why is OneDrive needed for Office?** Intune MAM marks all data in the app as either "corporate" or "personal." Data is considered "corporate" when it originates from a business location. For the Office apps, Intune MAM considers the following as business locations: email (Exchange) or cloud storage (OneDrive app with a OneDrive for Business account).

### App protection policies

1. **What are app protection policies**? App protection policies are rules that ensure an organization's data remains safe or contained in a managed app. A policy can be a rule that is enforced when the user attempts to access or move "corporate" data, or a set of actions that are prohibited or monitored when the user is inside the app.

2. **What are examples of app protection policies?** See [here](../deploy-use/android-mam-policy-settings) for Android app protection policies and [here](../deploy-use/ios-mam-policy-settings) for iOS app protection policies.

### App protection features

1. **What is multi-identity support in MAM?** Multi-identity support is the ability for the Intune App SDK to only apply app protection policies to the work or school account signed into the app. If a personal account is signed into the app, the data is untouched.

  1. **What is the purpose of multi-identity support?** Multi-identity support allows apps with both "corporate" and consumer audiences (ie. the Office apps) to be released publicly with Intune app protection capabilities for the "corporate" accounts.

  2. **When does the MAM PIN screen show up?** The Intune MAM PIN screen only appears when the user is trying to access "corporate" data. For example, in the Word/Excel/PowerPoint apps, it would appear when the end-user attempts to open a document from OneDrive for Business (assuming you successfully deployed an app protection policy enforcing PIN).

  3. **What about Outlook and multi-identity?** Because Outlook has a combined email view of both personal and "corporate" emails, the Outlook app prompts for the Intune MAM PIN on launch.

2. **What is the Intune app PIN?** The Personal Identification Number (PIN) is a passcode used to verify that the correct user is accessing the organization's data in an application.

  1. **When is the user prompted to enter their PIN?** Intune's approach to app PIN is slightly different from that of other MAM providers. Intune MAM will only prompt for the user's app PIN when the user is about to access "corporate" data. In multi-identity apps such as Word/Excel/PowerPoint, the user is prompted for their PIN when they try to open a "corporate" document or file. In single-identity apps, such as line-of-business apps enlightened using the Intune App Wrapping Tool, the PIN is prompted at launch, because the Intune App SDK knows the user's experience in the app is always "corporate."

  2. **Is the PIN secure?** The PIN serves to allow only the correct user to access their organization's data in the app. Therefore, an end-user must sign in with their work or school account before they can set or reset their Intune app PIN. This authentication is handled by Azure Active Directory via secure token exchange and is not transparent to the Intune App SDK. From a security perspective, the best way to protect work or school data is to encrypt it. Encryption is not related to the app PIN, but is its own app protection policy.

  3. **How does MAM protect the app PIN against brute force attacks?** As part of the app PIN policy, the IT administrator can set the maximum number of times a user can try to authenticate their PIN before locking the app. After the number of attempts has been met, the Intune App SDK can wipe the "corporate" data in the app.

3. **What about encryption?** IT administrators can deploy an app protection policy that requires app data to be encrypted. As part of the policy, the IT administrator can also specify when the content is encrypted.

  1. **How is "corporate" data encrypted?** On iOS devices, Intune MAM encrypts data using the iOS system's encryption technology. On Android devices, Intune MAM encrypts data using a secured scheme that is based on an open-source algorithm for Android encryption.

  2. **What gets encrypted?** Only data marked as "corporate" by the Intune App SDK is encrypted according to the IT administrator's app protection policy. Intune MAM marks all data in the app as either "corporate" or "personal." Data is considered "corporate" when it originates from a business location. For the Office apps, Intune MAM considers the following as business locations: email (Exchange) or cloud storage (OneDrive app with a OneDrive for Business account). For line-of-business apps enlightened by the Intune App Wrapping Tool, all app data is considered "corporate."

4. **How does Intune remotely wipe data?** Intune MAM can wipe app data in two different ways: full wipe and selective wipe. For more information about remote wipe, read this [article](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune).

  1. **What is full wipe?** Full wipe removes all user data and settings from **the device** by restoring the device to its factory default settings. The device is removed from Intune.
  >[!NOTE]
  > Full wipe can only be achieved on devices enrolled with Intune mobile device management (MDM).

  2. **What is selective wipe?** Selective wipe only removes data tagged as "corporate" by the Intune App SDK and leaves personal data on the device intact. Selective wipe can only be achieved in Intune MAM apps.

  3. **How quickly does selective wipe happen?** If the user is using the app when selective wipe is initiated, the Intune App SDK checks every 30 minutes for a selective wipe request from the Intune MAM service. It also checks for selective wipe when the user launches the app for the first time and signs in with their work or school account.

5. **Why don't On-Premises (on-prem) services work with MAM?** Intune MAM depends on the identity of the user to be consistent between the application and the Intune App SDK. The only way to guarantee that is through modern authentication. There are scenarios in which apps may work with an on-prem configuration, but they are neither consistent nor guaranteed.  

6. **Is there a secure way to open web links from managed apps?** Yes! The IT administrator can deploy and set app protection policy for the [Intune Managed Browser app](../deploy-use/manage-internet-access-using-managed-browser-policies), a web browser developed by Microsoft Intune that can be managed easily with Intune. The IT administrator can require all web links in MAM apps to be opened using the Managed Browser app.


### MAM app experience on Android

1. **Why is the Company Portal app needed on Android devices for MAM without device enrollment?** Much of MAM functionality is built into the Company Portal app. Device enrollment is _not required_ even though the Company Portal app is. The end-user just needs to have the Company Portal app installed on the device.

### MAM app experience on iOS

1. **I am able to use the iOS share extension to open work or school data in unmanaged apps, even with the data transfer policy set to "managed apps only" or "no apps." Doesn't this leak data?** Intune MAM without device enrollment cannot control the iOS share extension without managing the device. Therefore, the Intune App SDK _**encrypts "corporate" data that is shared with unmanaged apps**_ before allowing it to be transferred out of the MAM app. You can validate this by attempting to open the "corporate" file outside of the managed app. The file should be encrypted and unable to be opened outside the managed app.


## Common Intune administrative issues

1. **Issue:** App protection policy without device enrollment, made in the Azure portal, is not applying to the Skype for Business app on iOS and Android devices.

  **Resolution**: Skype for Business must be set up for modern authentication.  Please follow instructions in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) to set up modern authentication for Skype.

2. **Issue:** App protection policies are not applying to any [supported Office App](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) for any user.

  **Resolution**: Confirm that the user is licensed for Intune and the Office apps are targeted by a deployed app protection policy. It can take up to 8 hours for a newly deployed app protection policy to be applied.

3. **Issue:** IT administrator user is unable to configure app protection policies in Azure Portal.

  **Resolution**:

  The following user roles have access to the Azure Portal:

  - Global administrator, which you can set up in the [Office Portal](http://portal.office.com/)
  - Owner, which you can set up in the [Azure Portal](https://portal.azure.com/).
  - Contributor, which you can set up in the [Azure Portal](https://portal.azure.com/).<br><br>

  Refer to [Get ready to configure mobile app management policies with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) for help  setting up these roles.

4. **Issue:** Admin console reports do not show user account(s) to which app protection policy was recently deployed.

  **Resolution**: If a user is newly targeted by an app protection policy, it can take up to 24 hours for that user to show up in reports as a targeted user.

5. **Issue:** Policy changes/updates can take up to 8 hours to apply.  

  **Resolution**: End-user can log out of the app and log back in to force sync with service .  

6. **Issue:** App protection policy is not applying to Apple DEP devices.

  **Resolution**: Please ensure you are using User Affinity with Apple Device Enrollment Program (DEP). User Affinity is required for any app that requires user authentication under DEP.
Refer to [Enroll corporate-owned Device Enrollment Program iOS devices](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) for more information on iOS DEP enrollment.

## Common end-user dialogs

### MAM dialogs on iOS

Dialog/Error message | Cause | Remediation |
-- | --- | --- |
**App Not Set Up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Welcome to the Intune Managed Browser**: This app works best when managed by Microsoft Intune. You can always use this app to browse the web, and when it is managed by Microsoft Intune you gain access to additional data protection features. | Failure to detect required app protection policy for the Intune Managed Browser app. <br><br>The user can still use the app to browse the web, but the app is not managed by Intune. | Make sure an iOS app protection policy is deployed to the user's security group and targets the Intune Managed Browser app.
**Sign-in Failed**: We can't sign you in right now. Please try again later. | Failure to enroll the user with the MAM service after the user attempts to sign in with their work or school account. | Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Account Not Set Up**: Your organization has not set up your account to access work or school data. Please contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Device Non-Compliant**: This app cannot be used because you are using a jailbroken device. Contact your IT administrator for help. | Intune detected the user is on a jailbroken device. | Reset the device to default factory settings. Follow [these instructions](https://support.apple.com/en-us/HT201274) from the Apple support site.
**Internet Connection Required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Unknown Failure**: Try restarting this app. If the problem persists, contact your IT administrator for help. | An unknown failure occurred. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](/how-to-get-support-for-microsoft-intune).
**Accessing Your Organization's Data**: The work or school account you specified does not have access to this app. You may have to sign in with a different account. Contact your IT administrator for help. | Intune detects the user attempted to sign in with second work or school account that is different from the MAM enrolled account for the device. Only one work or school account can be managed by MAM at a time per device. | Have the user sign in with the account whose username is pre-populated by the sign-in screen. <br> <br> Or, have the user sign in with the new work or school account and remove the existing MAM enrolled account.
**Connection Issue**: An unexpected connection issue occurred. Check your connection and try again.  |  Unexpected failure. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](/how-to-get-support-for-microsoft-intune).
**Alert**: This app can no longer be used. Contact your IT administrator for more information. | Failure to validate the app's certificate. | Make sure the app version is up-to-date. <br><br> Reinstall the app.
**Error**: This app has encountered a problem and must close. If this error persists, please contact your IT administrator. | Failure to read the MAM app PIN from the Apple iOS Keychain. | Restart the device. Make sure the app version is up-to-date. <br><br> Reinstall the app.


### MAM dialogs on Android

Dialog/Error message | Cause | Remediation |
-- | --- | --- |
**App not set up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Failed app launch**: There was an issue launching your app. Try updating the app or the Intune Company Portal app. If you need help, contact your IT administrator. | Intune detected valid app protection policy for the app, but the app is crashing during MAM initialization. | Make sure the app version is up-to-date. <br><br> Make sure the Intune Company Portal app is installed and up-to-date on the device. <br><br> If the error persists, use the Company Portal app to send logs to Intune or create a support ticket [here](/how-to-get-support-for-microsoft-intune).
**No apps found**: There are no apps on this device that your organization allows to open this content. Contact your IT administrator for help. | The user tried to open work or school data with another app, but Intune cannot find any other managed apps that are allowed to open the data. | Make sure an Android app protection policy is deployed to the user's security and targets at least one other MAM-enabled app that can open the data in question.
**Sign-in failed**: Try to sign in again. If this problem persists, contact your IT administrator for help. | Failure to authenticate the account with which the user attempted to sign in. | Make sure the user signs in with the work or school account that is already enrolled with the Intune MAM service (the first work or school account that was successfully signed into in this app). <br><br> Clear the app's data. <br><br> Make sure the app version is up-to-date. <br><br> Make sure the Company Portal version is up-to-date.
**Internet connection required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Device non-compliant**: This app can't be used because you are using a rooted device. Contact your IT administrator for help. | Intune detected the user is on a rooted device. | Reset the device to default factory settings.
**Account not set up**: This app must be managed by Microsoft Intune, but your account has not been set up. Contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Unable to register the app**: This app must be managed by Microsoft Intune, but we were unable to register this app at this time. Contact your IT administrator for help. | Failure to automatically enroll the app with the MAM service when app protection policy is required. | Clear the app's data. <br><br> Send logs to Intune through the Company Portal app or file a support ticket [here](/how-to-get-support-for-microsoft-intune).





### See also
- [Validating your mobile application management setup](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Get ready to configure mobile app management policies with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
