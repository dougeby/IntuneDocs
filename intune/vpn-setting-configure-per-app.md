---
# required metadata

title: Set up Per-App VPN in Microsoft Intune for iOS devices
titleSuffix: "Intune on Azure"
description: Specify which managed apps can use your VPN on Intune managed iOS devices.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/5/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up Per-App VPN in Microsoft Intune for iOS devices

You can specify which managed apps can use your Virtual Private Network (VPN) on Intune managed iOS devices. When you specify a Per-APP VPN in Intune, an end user automatically connects through your VPN when accessing corporate documents.

## Prerequisites for the Per-App VPN

To prove its identity, the VPN server presents the certificate that must be accepted without a prompt by the device. To ensure the automatic approval of the certificate, create a trusted certificate profile that contains the VPN server's root certificate issued by the Certificate Authority (CA). 

Export the certificate and add the CA.

1. Open the administration console on your VPN server.
2. Verify that your VPN server uses Certificate-based Authentication. 
3. Export the trusted root certificate file. It has a .cer extension, and you add it when creating a trusted certificate profile.
4. Add the name of the CA that issued the certificate for authentication to the VPN server.
    If the CA presented by the device matches one of the CAs in the Trusted CA list on the VPN server, then the VPN server successfully authenticates the device.

## Create a  group for your VPN users

Create or choose an existing group in Azure Active Directory (Azure AD) to contain the members who have access to the per-App VPN.

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**.
2. Choose **Groups** and click **New group**.
3. Type the **Name** of the group. 
4. Type the **Description** of the group. 
5. Select **Assigned** for the **Membership type**.
6. Select **No** for **Enable Office features**.
7. Search for the VPN users by name or email address in the **Members** blade.
8. Select each user and click **Select**.
9. Click **Create**

## Create a trusted certificate profile

Import the VPN server's root certificate issued by the CA into a profile created in Intune. The trusted certificate profile instructs the iOS device to automatically trust the CA that the VPN server presents.

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**.
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **+ Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **Trusted certificate** for the **Profile type**.
4. Click the folder icon and browse to your VPN certificate (.cer file) that you exported from your VPN administration console. Click OK
5. Click **Create**.

    ![Create a trusted certificate profile](media\vpn-per-app-create-trusted-cert.png)

## Create a SCEP certificate profile

The trusted root certificate profile allows the iOS to automatically trust the VPN Server. The SCEP certificate provides credentials from the iOS VPN client to the VPN server. The certificate allows the device to silently authenticate without prompting the iOS devise user for a username and password. 

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**. 
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **+ Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **SCEP certificate** for the **Profile type**.
4. Select **Years** and type `2` for **Certificate validity period**.
5. Select **Common name** for **Subject name format**.
6. Select **User principle name (UPN)** for **Subject alternative name**.
7. Select **Digital signature** and **Key encipherment** for **Key usage**.
8. Select **2048** for **Key size (bits)**.
9. Click Root Certificate and select a SCEP certificate. Click **OK**.
10. Type `Client Authentication` in **Name** for **Extended key usage**.
11. Type `1.3.6.1.5.5.7.3.2` in **Object Identifier**.
12. Click **Add**.
13. Type the ***Server URL*** and click **Add**.
14. Click **OK**.
15. Click **Create**.

    ![Create a SCEP certificate profile](media\vpn-per-app-create-SCEP-cert.png)

## Create a Per-App VPN profile

The VPN profile contains the SCEP certificate carrying the client credentials, the connection information to the VPN, and the Per APP VPN flag to enable the Per App VPN feature for use by the iOS application.

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**.
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **+ Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **VPN** for the **Profile type**.
4. Select **Base VPN**. In **Base VPN**:
    1. Type the **Connection name**.
    2. Type the **IP address or FQDN**.
    3. Select **Certificates** for the **Authentication method**.
    4. Select the SCEP certificate under **Authentication certificate** and click **OK**.
    5. Select your VPN for the **Connection type**.
    6. If necessary, configure the attributes for your VPN.
    7. Select for **Disable Split** tunneling.
5. Click **Automatic VPN**. In **Automatic VPN**:
    1. Select **Per-App VPN** for the **Type of automatic VPN**.
    2. Type the URL for the VPN and click **Add**.
    3. Click **OK**.
6. Click **OK**.
7. Click **Create**.

    ![Create a Per-App VPN profile](media\vpn-per-app-create-VPN-profile.png)


## Associate an app with the VPN profile

After adding your VPN profile, associate the app and Azure AD group to the profile.

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**.
2. Choose **Mobile Apps**.
3. Click **Apps**.
4. Select the app from the list of apps.
5. Click **Assignments.**
6. Click **Select groups**, select the group you defined earlier. Click **Select**.
7. Select **Required** for the **Type** in the **Assignments** blade.
8. Select your VPN definition for the **VPNS**.
 
    > [!NOTE]  
    > Sometimes the VPN definition takes up to a minute to retrieve the value. Wait for 3-5 minutes before your click **Save**.

9. Click **Save**.

    ![Associate an app with the VPN](media\vpn-per-app-App-to-VPN.png)

## Verify the connection on the iOS device

With your Per-App VPN set-up and associated with your app, verify the connection works from a device.

### Before you attempt to connect

 - Make sure you’re running iOS 7 or later.
 - Make sure you deploy *all* of the above mentioned policies to the same group of users. Failure to do so will most definitely break the Per-App VPN experience.  
 - Makes sure you have the supported third-party VPN app installed. The following VPN apps are supported:
    - Juniper
    - Checkpoint
    - F5
    - SonicWall

### Connect using the Per-App VPN

Verify the zero-touch experience by connecting without having to select the VPN or type your credentials. The zero-touch experience means:

 - The device does not ask you to trust the VPN server. That is, you do see the **Dynamic Trust** dialog box.
 - You do not have to type credentials.
 - You are connected to the VPN after tapping the connect button.

Verify the connection on an iOS device.

1. Tap the VPN app.
2. Tap on **Connect**.  
The VPN successfully connects without any extra prompts.

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## Next steps

To review iOS settings, see [VPN settings for iOS devices in Microsoft Intune](vpn-settings-ios.md).  
To learn more about VPN setting and Intune, see [How to configure VPN settings in Microsoft Intune](vpn-settings-configure.md).