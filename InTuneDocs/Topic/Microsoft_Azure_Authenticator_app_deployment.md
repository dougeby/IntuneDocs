---
title: Microsoft Azure Authenticator app deployment
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: db9a294a-8409-450b-9b83-808a43a64788
author: robstackmsft
robots: noindex,nofollow
---
# Microsoft Azure Authenticator app deployment
Microsoft Azure Authenticator is a part of the Microsoft Enterprise Mobility Suite (EMS) of applications. Use this app to let your users and their devices securely connect to Microsoft services such as Office 365. This app is required by the access control, data protection, and compliance features of Microsoft Intune.

This app also streamlines enrollment for your users, providing single sign-on (SSO) and multi-factor authentication (MFA) for apps on your devices.

For the best experience, you should deploy the app as part of Intune device enrollment. Starting in September, Intune and Configuration Manager hybrid will automatically deploy the Azure Authenticator app for Android  devices  from Google Play as a required install.

[Click here](https://msdn.microsoft.com/en-us/library/azure/dn858223.aspx) to find out more about the Azure Authenticator app.

## Why is Intune deploying this app?
Later this year, Microsoft will issue an update to the  Microsoft Intune Company Portal app to simplify the enrollment experience, including removing the ‘Microsoft workaccount’ and ‘Name the certificate’ prompts required during Intune enrollment on Android devices.

![](../Image/Azure_Authenticator_certificate.jpg)

When the company portal is updated, Android devices without the Azure Authenticator app installed will:

-   Lose single sign-on for Intune

-   Lose single sign-on for Office apps

-   Be quarantined if conditional access is enabled

### Recommendations for IT Administrators
To avoid these problems, you should deploy the Azure Authenticator app as a required installation to Android devices before the company portal update. You can do this in two ways:

-   Tell your end-users to install the Microsoft Azure Authenticator app now from [Google Play](https://play.google.com/store/apps/details?id=com.azure.authenticator)

-   Manually deploy the Azure Authenticator app from Google Play as a required install to all users.

Alternatively, tell your end-users to follow the required application notification to install the Azure Authenticator app from Google Play after the September updates of Microsoft Intune and Microsoft System Center Configuration Manager are released.

![](../Image/Azure_Authenticator_required_install.jpg)

Although we recommend that this feature remains enabled, if your organization does not use the single sign-on or conditional access features, you can disable the automatic deployment of the Azure Authenticator app from the Intune console as follows:

**Intune:** Go to the **Mobile Device Management** &gt; **Android** node in the Intune console

**Configuration Manager hybrid:** Go to the **Microsoft Intune Subscription Properties** page in the Configuration Manager console

## What to do if your users are quarantined
If users with Android devices who are targeted by a conditional access policy don’t install the Azure Authenticator app, they will be quarantined from Exchange email when the company portal updates on their devices.

To regain access, users must click the link in the quarantine email they receive to access the company portal app and then follow the instructions to complete enrollment update and enrollment activation.

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation_for_Microsoft_Intune.md)

