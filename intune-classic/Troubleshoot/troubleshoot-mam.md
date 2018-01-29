---
# required metadata

title: Troubleshoot mobile application management 
description: This topic describes some troubleshooting tips for conditional access deployments.
keywords:
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
#ms.reviewer: joglocke
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot mobile application management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

If you are having problems with Intune mobile application management, start here. This topic contains some common problems and questions you might have and provides solutions and answers.

If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.


## Common IT administrator issues

These are common issues an IT administrator may experience with using Intune app protection policy.

| Issue | Description | Resolution |
| -- | -- | -- |
| Policy not applied to Skype for Business | App protection policy without device enrollment, made in the Azure portal, is not applying to the Skype for Business app on iOS and Android devices. | Skype for Business must be set up for modern authentication.  Please follow instructions in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) to set up modern authentication for Skype. |
| Office app policy not applied | App protection policies are not applying to any [supported Office App](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) for any user. | Confirm that the user is licensed for Intune and the Office apps are targeted by a deployed app protection policy. It can take up to 8 hours for a newly deployed app protection policy to be applied. |
| Admin can't configure app protection policy in Azure portal | IT administrator user is unable to configure app protection policies in Azure Portal. | The following user roles have access to the Azure Portal: <ul><li>Global administrator, which you can set up in the [Office Portal](http://portal.office.com/)</li><li>Owner, which you can set up in the [Azure Portal](https://portal.azure.com/).</li><li>Contributor, which you can set up in the [Azure Portal](https://portal.azure.com/).</li></ul>  Refer to [Get ready to configure mobile app management policies with Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) for help  setting up these roles.|
|User accounts missing from app protection policy reports | Admin console reports do not show user accounts to which app protection policy was recently deployed. | If a user is newly targeted by an app protection policy, it can take up to 24 hours for that user to show up in reports as a targeted user. |
| Policy changes not working | Changes and updates to app protection policy can take up to 8 hours to apply. | If applicable, the end-user can log out of the app and log back in to force sync with service. |
| App protection policy not working with DEP | App protection policy is not applying to Apple DEP devices. | Please ensure you are using User Affinity with Apple Device Enrollment Program (DEP). User Affinity is required for any app that requires user authentication under DEP. <br><br>Refer to [Enroll corporate-owned Device Enrollment Program iOS devices](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md) for more information on iOS DEP enrollment.|
| Data transfer policy not working with iOS | The **Allow app to transfer data to other apps** and **Allow app to receive data from other apps** policies do not successfully manage data transfer in iOS. | See [Manage data transfer between iOS apps with Microsoft Intune](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## Common end-user issues

Common end-user issues are broken down in the following categories:

* **Normal usage scenarios**: An end-user might experience these scenarios on apps that have Intune app protection policy. These are not actual issues, but may be perceived as bugs or errors.

* **Normal usage dialogs**: These are usage dialogs an end-user might see in apps that have Intune app protection policy. These messages and dialogs do **not** indicate an error or bug.

* **Error messages and dialogs**: These are error messages and dialogs an end-user might see on apps that have Intune app protection policy. These often indicate an error was made by the IT administrator or a bug with Intune app protection.



### Normal usage scenarios

Platform | Scenario | Explanation |
---| --- | --- |
iOS | The end-user can use the iOS share extension to open work or school data in unmanaged apps, even with the data transfer policy set to **Managed apps only** or **No apps.** Doesn't this leak data? | Intune app protection policy cannot control the iOS share extension without managing the device. Therefore, **Intune encrypts "corporate" data before sharing it outside the app**. You can validate this by attempting to open the "corporate" file outside of the managed app. The file should be encrypted and unable to be opened outside the managed app.
Android | Why does the end-user **need to install the Company Portal app**, even if I'm using MAM app protection without device enrollment?  | On Android, much of app protection functionality is built into the Company Portal app. **Device enrollment is not required even though the Company Portal app is always required**. For app protection without enrollment, the end-user just needs to have the Company Portal app installed on the device.

### Normal usage dialogs

Platform | Message or dialog | Explanation |
--- | --- | --- |
iOS, Android | **Sign-in**: To protect its data, your organization needs to manage this app. To complete this action, sign in with your work or school account. | The end-user must sign in with their work or school account in order to use this app, which requires app protection policy. In order for policy to apply, the user must authenticate against Azure Active Directory.
iOS, Android |**Restart Required**: Your organization is now protecting its data in this app. You need to restart the app to continue. | The app has just received Intune app protection policy and must restart in order for the policy to apply.
iOS, Android |**Action Not Allowed**: Your organization only allows you to open work or school data in this app. | The IT administrator has set the **Allow app to receive data from other apps** to **Managed apps only**. Therefore, the end-user can only transfer data into this app from other apps that have app protection policy.
iOS, Android |**Action Not Allowed**: Your organization only allows you to transfer its data to other managed apps. | The IT administrator has set the **Allow app to transfer data to other apps** to **Managed apps only**. Therefore, the end-user can only transfer data out of this app to other apps that have app protection policy.
iOS, Android |**Wipe Alert**: Your organization has removed its data associated with this app. To continue, restart the app. | The IT administrator has initiated an app wipe using Intune app protection.
Android | **Company Portal required**: To use your work or school account with this app, you must install the Intune Company Portal app. Tap “Go to store” to continue. | On Android, much of app protection functionality is built into the Company Portal app. **Device enrollment is not required even though the Company Portal app is always required**. For app protection without enrollment, the end-user just needs to have the Company Portal app installed on the device.


### Error messages and dialogs on iOS


Error message or dialog | Cause | Remediation |
-- | --- | --- |
**App Not Set Up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Welcome to the Intune Managed Browser**: This app works best when managed by Microsoft Intune. You can always use this app to browse the web, and when it is managed by Microsoft Intune you gain access to additional data protection features. | Failure to detect required app protection policy for the Intune Managed Browser app. <br><br>The user can still use the app to browse the web, but the app is not managed by Intune. | Make sure an iOS app protection policy is deployed to the user's security group and targets the Intune Managed Browser app.
**Sign-in Failed**: We can't sign you in right now. Please try again later. | Failure to enroll the user with the MAM service after the user attempts to sign in with their work or school account. | Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Account Not Set Up**: Your organization has not set up your account to access work or school data. Please contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Device Non-Compliant**: This app cannot be used because you are using a jailbroken device. Contact your IT administrator for help. | Intune detected the user is on a jailbroken device. | Reset the device to default factory settings. Follow [these instructions](https://support.apple.com/HT201274) from the Apple support site.
**Internet Connection Required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Unknown Failure**: Try restarting this app. If the problem persists, contact your IT administrator for help. | An unknown failure occurred. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](how-to-get-support-for-microsoft-intune.md).
**Accessing Your Organization's Data**: The work or school account you specified does not have access to this app. You may have to sign in with a different account. Contact your IT administrator for help. | Intune detects the user attempted to sign in with second work or school account that is different from the MAM enrolled account for the device. Only one work or school account can be managed by MAM at a time per device. | Have the user sign in with the account whose username is pre-populated by the sign-in screen. <br> <br> Or, have the user sign in with the new work or school account and remove the existing MAM enrolled account.
**Connection Issue**: An unexpected connection issue occurred. Check your connection and try again.  |  Unexpected failure. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](how-to-get-support-for-microsoft-intune.md).
**Alert**: This app can no longer be used. Contact your IT administrator for more information. | Failure to validate the app's certificate. | Make sure the app version is up-to-date. <br><br> Reinstall the app.
**Error**: This app has encountered a problem and must close. If this error persists, please contact your IT administrator. | Failure to read the MAM app PIN from the Apple iOS Keychain. | Restart the device. Make sure the app version is up-to-date. <br><br> Reinstall the app.


### Error messages and dialogs on Android

Dialog/Error message | Cause | Remediation |
-- | --- | --- |
**App not set up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an Android app protection policy is deployed to the user's security group and targets this app.
**Failed app launch**: There was an issue launching your app. Try updating the app or the Intune Company Portal app. If you need help, contact your IT administrator. | Intune detected valid app protection policy for the app, but the app is crashing during MAM initialization. | Make sure the app version is up-to-date. <br><br> Make sure the Intune Company Portal app is installed and up-to-date on the device. <br><br> If the error persists, use the Company Portal app to send logs to Intune or create a support ticket [here](how-to-get-support-for-microsoft-intune.md).
**No apps found**: There are no apps on this device that your organization allows to open this content. Contact your IT administrator for help. | The user tried to open work or school data with another app, but Intune cannot find any other managed apps that are allowed to open the data. | Make sure an Android app protection policy is deployed to the user's security and targets at least one other MAM-enabled app that can open the data in question.
**Sign-in failed**: Try to sign in again. If this problem persists, contact your IT administrator for help. | Failure to authenticate the account with which the user attempted to sign in. | Make sure the user signs in with the work or school account that is already enrolled with the Intune MAM service (the first work or school account that was successfully signed into in this app). <br><br> Clear the app's data. <br><br> Make sure the app version is up-to-date. <br><br> Make sure the Company Portal version is up-to-date.
**Internet connection required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Device noncompliant**: This app can't be used because you are using a rooted device. Contact your IT administrator for help. | Intune detected the user is on a rooted device. | Reset the device to default factory settings.
**Account not set up**: This app must be managed by Microsoft Intune, but your account has not been set up. Contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Unable to register the app**: This app must be managed by Microsoft Intune, but we were unable to register this app at this time. Contact your IT administrator for help. | Failure to automatically enroll the app with the MAM service when app protection policy is required. | Clear the app's data. <br><br> Send logs to Intune through the Company Portal app or file a support ticket [here](how-to-get-support-for-microsoft-intune.md).




### See also
- [Validating your mobile application management setup](../deploy-use/validate-mobile-application-management.md)
- [Get ready to configure mobile app management policies with Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md)
