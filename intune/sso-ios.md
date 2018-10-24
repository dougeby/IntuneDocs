---
# required metadata

title: Add single sign-on for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: In Microsoft Intune, create, configure, allow, or enable iOS devices to use single sign-on (SSO) instead of password for authentication to your organization's resources and data. To use SSO, create a device configuration profile, and enter the UPN, device ID, your apps, and a certificate to authenticate the user and the device. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use single sign-on iOS device in Microsoft Intune

Most Line of Business (LOB) apps require some level of user authentication to support security. In many cases, this authentication requires the user to enter the same credentials multiple times, which is frustrating. To improve the user experience, developers can create apps that use single sign-on, reducing the number of times a user must enter credentials.

This article shows you how to turn on single sign-on for iOS devices using a device configuration profile in Microsoft Intune.

## Before you begin

Be sure you have an app coded to look for the user credential store in the single sign-on payload on the iOS device.

## Configure Intune for iOS device single sign-on

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Choose **Device configuration** > **Profiles** > **Create profile**.
3. Enter the the following settings:

    - **Name**: Enter a name for the profile, such as `ios sso profile`.
    - **Description**: Enter a description with key terms to help you fiind the profile in the list.
    - **Platform**: Choose **iOS**.
    - **Profile type**: Choose **Device features**.

4. Choose **Single Sign On**.

    ![Single Sign On pane](./media/sso-blade.png)

5. Enter the following settings: 

    - **Username attribute from AAD**: Intune looks for this attribute for each user in Azure AD. Intune then populates the respective field (such as UPN) before generating the XML payload that gets installed on the device. Your options:
    
        - **User Principal Name**: The UPN is parsed in the following way:

            ![Username attribute](media/User-name-attribute.png)

            You can also overwrite the realm with the text you enter in the **Realm** text box.

            For example, Contoso might have several subregions such as Europe, Asia, and North America. They might want their users in Asia to use the SSO payload, and the app requires the UPN in `username@asia.contoso.com` format. In this case, if you select **User Principal Name**, by default the realm for each user is taken from Azure AD, which may be *contoso.com*. So for users in Asia specially, you can create this payload and overwrite the realm with the value *asia.contoso.com*. Now the end user's UPN becomes username@asia.contoso.com, instead of username@contoso.com.

        - **Intune Device ID**: Intune automatically selects the Intune Device ID. 

            By default, apps only need to use the device ID. But if your app uses the realm *and* the device ID, you can type the realm in the **Realm** text box.

            > [!NOTE]
            > By default, keep the realm empty if you use device ID.

    - **Realm**: The domain portion of the URL.
    
    - **URL prefixes that will use Single Sign On**: **Add** any URLs in your organization that require user single sign-on authentication. 

        For example, when a user connects to any of these sites, the iOS device uses the single sign-on credentials. The user doesn't need to enter any additional credentials. However, if you have multi-factor authentication enabled, users are required to enter the second authentication.

        > [!NOTE]
        > These URLs must be properly formatted FQDN. Apple requires the URLs to be in the `http://<yourURL.domain>` format.

        The URL matching patterns must begin with either `http://` or `https://`. A simple string match is performed, so the URL prefix `http://www.contoso.com/` doesn't match `http://www.contoso.com:80/`. With iOS 10.0 or later, however, a single wildcard \* may be used to enter all matching values. For example, `http://*.contoso.com/`  matches both `http://store.contoso.com/` and `http://www.contoso.com`.

        The patterns `http://.com` and `https://.com` match all HTTP and HTTPS URLs, respectively.
    
    - **Apps that will use Single Sign On**: **Add** apps on end users' devices that can use single sign-on. 

        The `AppIdentifierMatches` array must contain strings that match app bundle IDs. These strings may be exact matches (such as `com.contoso.myapp`), or enter a prefix match on the bundle ID using the \* wildcard character. The wildcard character must appear after a period character (.), and may appear only once, at the end of the string (for example: `com.contoso.*`). When a wildcard is included, any app whose bundle ID begins with the prefix is granted access to the account.

        Use **App Name** to enter a user-friendly name to help you identify the bundle ID.
    
    - **Credential renewal certificate**: If using certificates for authentication (not passwords), select the SCEP or PFX certificate that's deployed to the user as the authentication certificate. Typically, this is the same certificate that's deployed to the user for other profiles, such as VPN, Wi-Fi, or email.

6. Select **OK** > **OK** > **Create** to save your changes, and create the profile. Once created, it's shown in the **Device configuration - profiles** list. 

## Next steps

For additional device feature configuration information, see [How to configure device feature settings in Microsoft Intune](device-features-configure.md).

[Assign this profile](device-profile-assign.md) to your iOS devices.
