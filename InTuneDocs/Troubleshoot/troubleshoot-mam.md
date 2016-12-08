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





## Common IT administrator issues

1. **Issue:** App protection policy without device enrollment, made in the Azure portal, is not applying to the Skype for Business app on iOS and Android devices.

  **Resolution**: Skype for Business must be set up for modern authentication.  Please follow instructions in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) to set up modern authentication for Skype.

2. **Issue:** App protection policies are not applying to any [supported Office App](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) for any user.

  **Resolution**: Confirm that the user is licensed for Intune and the Office apps are targeted by a deployed app protection policy. It can take up to 8 hours for a newly deployed app protection policy to be applied.

3. **Issue:** IT administrator user is unable to configure app protection policies in Azure Portal.

  **Resolution**:

  The following user roles have access to the Azure Portal:

  - Global administrator, which you can set up in the [Office Portal](http://portal.office.com/)
  - Owner, which you can set up in the [Azure Portal](https://portal.azure.com/).
  - Contributor, which you can set up in the [Azure Portal](https://portal.azure.com/).<br>

  Refer to [Get ready to configure mobile app management policies with Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) for help  setting up these roles.

4. **Issue:** Admin console reports do not show user account(s) to which app protection policy was recently deployed.

  **Resolution**: If a user is newly targeted by an app protection policy, it can take up to 24 hours for that user to show up in reports as a targeted user.

5. **Issue:** Policy changes/updates can take up to 8 hours to apply.  

  **Resolution**: End-user can log out of the app and log back in to force sync with service .  

6. **Issue:** App protection policy is not applying to Apple DEP devices.

  **Resolution**: Please ensure you are using User Affinity with Apple Device Enrollment Program (DEP). User Affinity is required for any app that requires user authentication under DEP.
Refer to [Enroll corporate-owned Device Enrollment Program iOS devices](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md) for more information on iOS DEP enrollment.

## Common end-user issues

### Issues on iOS

Dialog/Error message | Cause | Remediation |
-- | --- | --- |
**App Not Set Up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Welcome to the Intune Managed Browser**: This app works best when managed by Microsoft Intune. You can always use this app to browse the web, and when it is managed by Microsoft Intune you gain access to additional data protection features. | Failure to detect required app protection policy for the Intune Managed Browser app. <br><br>The user can still use the app to browse the web, but the app is not managed by Intune. | Make sure an iOS app protection policy is deployed to the user's security group and targets the Intune Managed Browser app.
**Sign-in Failed**: We can't sign you in right now. Please try again later. | Failure to enroll the user with the MAM service after the user attempts to sign in with their work or school account. | Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Account Not Set Up**: Your organization has not set up your account to access work or school data. Please contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Device Non-Compliant**: This app cannot be used because you are using a jailbroken device. Contact your IT administrator for help. | Intune detected the user is on a jailbroken device. | Reset the device to default factory settings. Follow [these instructions](https://support.apple.com/en-us/HT201274) from the Apple support site.
**Internet Connection Required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Unknown Failure**: Try restarting this app. If the problem persists, contact your IT administrator for help. | An unknown failure occurred. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](/how-to-get-support-for-microsoft-intune.md).
**Accessing Your Organization's Data**: The work or school account you specified does not have access to this app. You may have to sign in with a different account. Contact your IT administrator for help. | Intune detects the user attempted to sign in with second work or school account that is different from the MAM enrolled account for the device. Only one work or school account can be managed by MAM at a time per device. | Have the user sign in with the account whose username is pre-populated by the sign-in screen. <br> <br> Or, have the user sign in with the new work or school account and remove the existing MAM enrolled account.
**Connection Issue**: An unexpected connection issue occurred. Check your connection and try again.  |  Unexpected failure. | Wait a while and try again. If the error persists, create a support ticket with Intune [here](/how-to-get-support-for-microsoft-intune.md).
**Alert**: This app can no longer be used. Contact your IT administrator for more information. | Failure to validate the app's certificate. | Make sure the app version is up-to-date. <br><br> Reinstall the app.
**Error**: This app has encountered a problem and must close. If this error persists, please contact your IT administrator. | Failure to read the MAM app PIN from the Apple iOS Keychain. | Restart the device. Make sure the app version is up-to-date. <br><br> Reinstall the app.


### Issues on Android

Dialog/Error message | Cause | Remediation |
-- | --- | --- |
**App not set up**: This app has not been set up for you to use. Contact your IT administrator for help. | Failure to detect required app protection policy for the app. |Make sure an iOS app protection policy is deployed to the user's security group and targets this app.
**Failed app launch**: There was an issue launching your app. Try updating the app or the Intune Company Portal app. If you need help, contact your IT administrator. | Intune detected valid app protection policy for the app, but the app is crashing during MAM initialization. | Make sure the app version is up-to-date. <br><br> Make sure the Intune Company Portal app is installed and up-to-date on the device. <br><br> If the error persists, use the Company Portal app to send logs to Intune or create a support ticket [here](/how-to-get-support-for-microsoft-intune.md).
**No apps found**: There are no apps on this device that your organization allows to open this content. Contact your IT administrator for help. | The user tried to open work or school data with another app, but Intune cannot find any other managed apps that are allowed to open the data. | Make sure an Android app protection policy is deployed to the user's security and targets at least one other MAM-enabled app that can open the data in question.
**Sign-in failed**: Try to sign in again. If this problem persists, contact your IT administrator for help. | Failure to authenticate the account with which the user attempted to sign in. | Make sure the user signs in with the work or school account that is already enrolled with the Intune MAM service (the first work or school account that was successfully signed into in this app). <br><br> Clear the app's data. <br><br> Make sure the app version is up-to-date. <br><br> Make sure the Company Portal version is up-to-date.
**Internet connection required**: You must be connected to the Internet to verify that you can use this app. | The device is not connected to the Internet. | Connect the device to a WiFi or Data network.
**Device non-compliant**: This app can't be used because you are using a rooted device. Contact your IT administrator for help. | Intune detected the user is on a rooted device. | Reset the device to default factory settings.
**Account not set up**: This app must be managed by Microsoft Intune, but your account has not been set up. Contact your IT administrator for help. | The user account does not have an Intune A Direct license. | Make sure the user's account has an Intune license assigned in the [Office portal](http://portal.office.com).
**Unable to register the app**: This app must be managed by Microsoft Intune, but we were unable to register this app at this time. Contact your IT administrator for help. | Failure to automatically enroll the app with the MAM service when app protection policy is required. | Clear the app's data. <br><br> Send logs to Intune through the Company Portal app or file a support ticket [here](/how-to-get-support-for-microsoft-intune.md).





### See also
- [Validating your mobile application management setup](../deploy-use/validate-mobile-application-management.md)
- [Get ready to configure mobile app management policies with Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
