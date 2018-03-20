---
# required metadata

title: Manage transferring data between iOS apps
titlesuffix: Microsoft Intune
description: Understand how to use mobile app management policies in Microsoft Intune to manage data transfers between apps.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure


---

# How to manage data transfer between iOS apps in Microsoft Intune
## Manage iOS apps
Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.  You can manage iOS apps in the following ways:

-   Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps. See [all the Intune-managed apps you can manage with app protection policy](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   You can also deploy and manage apps through the **MDM channel**.  This requires that the devices are enrolled in the MDM solution. These can be **policy-managed**  apps or other managed  apps.

The **Open in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**. Open in management restrictions are set in configuration settings and deployed using your MDM solution.  When the user installs the deployed app, the restrictions you set are applied.

##  Using app protection with iOS apps
App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:

-   **Employee owned devices not managed by any MDM solution:** You can set the app protection policy settings to **Allow app to transfer data to only Policy Managed apps**. The Open-In behavior in a Policy Managed app will only present other Policy Managed apps as an option for sharing. If a user tries to send a policy protected file as an attachment from OneDrive in the native mail, that file will be unreadable.

-   **Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed  automatically. To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting. You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.   

-   **Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.
To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-emm) walkthrough.  When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.

## Configure user UPN setting for Microsoft Intune or third-party EMM
Configuring the user UPN setting is **required** for devices that are managed by Intune or a third-party EMM solution. The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:

1.  In the [Azure portal](https://portal.azure.com), [create and assign an app protection policy](app-protection-policies.md) for iOS. Configure policy settings per your company requirements and select the iOS apps that should have this policy.

2.  Deploy the apps and the email profile that you want managed through Intune or your third-party MDM solution using the generalized steps below. This experience is also covered by Example 1.

3.  Deploy the app  with the following app configuration settings:

      **key** = IntuneMAMUPN,  **value** = <username@company.com>

      Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Deploy the **Open in management** policy using Intune or your third-party MDM provider to enrolled devices.


### Example 1: Admin experience in Intune or third-party MDM console

1. Go to the admin console of Intune or your third-party MDM provider. Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.

2. In the Application Configuration section, enter the following setting:

  **key** = IntuneMAMUPN,  **value** = <username@company.com>

  The exact syntax of the key/value pair may differ based on your third-party MDM provider. The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.

|Third-party MDM provider| Configuration Key | Value Type | Configuration Value|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | String | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | String | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | String | ${userUPN} **or** ${userEmailAddress} |


### Example 2: End-user experience

1.  End user installs Microsoft Word app on the device.

2.  End user launches the managed native email app to access their email.

3.  End user tries to open document from native mail in Microsoft Word.

4.  When the Word app launches, the end user is prompted to log in using their work account.  This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.

    > [!NOTE]
    > The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.

5.  When the login is successful, the app protection policy settings are applied to the Word app.

6.  Now the data transfer succeeds and the document is tagged with a corporate identity in the app. In addition, the data is treated in a work context and the policy settings are applied accordingly.

### Validate user UPN setting for third-party EMM

After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.

For example, the **Require app PIN** policy setting is easy to visually test on a device. If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.

First,  [create and assign an app protection policy](app-protection-policies.md) to the iOS app. See [Validate app protection policies](app-protection-policies-validate.md) for more information on how to test app protection policy.


### See also
[What is Intune app protection policy](app-protection-policy.md)
