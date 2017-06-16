---
# required metadata

title: How to configure Intune email settingstitleSuffix: "Intune on Azure"
description: Learn how to configure Intune to create connections to corporate email on devices you manage."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure email settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Email profiles can be used to configure devices you manage with the settings necessary to connect to , and synchronize with company email. This can help ensure that settings are standard across all of your devices, and also help to reduce support calls from end users who do not know the correct email settings.

The built-in mail client is supported for most platforms. Most third-party email apps are not currently supported.

You can use email profiles to configure the native email client on the following device types:

- Android Samsung KNOX Standard 4.0 and later
- Android for Work
- iOS 8.0 and later
- Windows Phone 8.1 and later
- Windows 10 (desktop) and Windows 10 Mobile

Use the information in this topic to learn the basics about configuring an email profile, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing email settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the email profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply email settings. Currently, you can choose one of the following platforms for email device settings:
	- **Android** (Samsung Android KNOX Standard only)
	- **Android for Work**
	- **iOS**
	- **Windows Phone 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Email**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android for Work and Samsung KNOX Standard settings](email-settings-android.md)
	- [iOS settings](email-settings-ios.md)
	- [Windows Phone 8.1 settings](email-settings-windows-phone-8-1.md)
	- [Windows 10 settings](email-settings-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).

## Further information

### Remove an email profile

If you want to remove an email profile from a device, edit the assignment and remove any groups of which the device is a member. Note that you cannot remove an email profile in this way if it is the only email profile on a device.

### Securing email access

You can help secure email profiles using one of two methods:

1. **Certificates** - When you create the email profile, you choose a certificate profile that you have previously created in Intune. This is known as the identity certificate, and is used to authenticate against a trusted certificate profile (or a root certificate) to establish that the user’s device is allowed to connect. The trusted certificate is assigned to the computer that authenticates the email connection, typically, the native mail server.
For more information about how to create and use certificate profiles in Intune, see [How to configure certificates with Intune](certificates-configure.md).
2. **User name and password** - The user authenticates to the native mail server by providing their user name and password.
The password is not contained in the email profile, so the user needs to supply this when they connect to email.


### How Intune handles existing email accounts

If the user has already configured an email account, the result of the Intune email profile assignment depends on the device platform:

- **iOS:** An existing, duplicate email profile is detected based on host name and email address. The duplicate email profile will blocks the assignment of an Intune profile. In this case, the Company Portal informs the user that they are not compliant and prompts the user to remove the manually configured profile. To help prevent this problem, instruct your users to enroll before installing an email profile, which allows Intune to set up the profile.
- **Windows:** An existing, duplicate email profile is detected based on host name and email address. Intune overwrites the existing email profile created by the user.
- **Android Samsung KNOX Standard** An existing, duplicate email profile is detected based on the email address, and overwrites it with the Intune profile.
Since Android does not use host name to identify the profile, we recommend that you not create multiple email profiles to use on the same email address on different hosts, as these overwrite each other.
- **Android for Work**
Intune provides two Android for Work email profiles, one for each of the Gmail and Nine Work email apps. These apps are available in the Google Play Store, and install in the device work profile, so they can't result in duplicate profiles. Both apps support connections to Exchange. To enable the email connectivity, deploy one of these email apps to your users' devices, and then create and deploy the appropriate email profile. Email apps such as Nine Work might not be free. Review the app’s licensing details or contact the app company with any questions.

### Update an email profile

If you make changes to an email profile you previously assigned, end users might see a message asking them to approve the reconfiguration of their email settings.
