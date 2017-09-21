---
# required metadata

title: Set up Per-App VPN in Microsoft Intune for iOS devices
titleSuffix: "Intune on Azure"
description: Specify which managed apps can use your VPN on Intune managed iOS devices.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/21/2017
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

You can specify which managed apps can use your VPN on Intune managed iOS devices. When you specify a Per-APP VPN in Intune, an end user automatically connects through your VPN when accessing corporate documents.

## Prerequisites

To prove its identity, the VPN server presents the certificate that must be accepted without a prompt by the device. To ensure the automatic approval of the certificate, provision a trusted certificate profile that contains the VPN server's root certificate issued by the Certificate Authority (CA). 

You need to:

 - Export a trusted root certificate exported from your VPN server.  
Verify that your VPN server uses Certificate-based Authentication. The root certificate is issued by the CA to the VPN server. Go to your VPN’s admin console and export the certificate.
 - Add the name of the Certificate Authority (CA) that issued the certificates for authentication.  
If the CA presented by the device matches one of the CAs in the Trusted CA list on the VPN server, then the VPN server successfully authenticates the device.

add two questions:

are coming from a trusted source
and who are you?
add a step about creating a group. (create a test group .... and then make sure the group is the same in the later step.)

## Create a trusted certificate profile

Import the VPN server's root certificate issued by the CA into a profile created in Intune. The trusted certificate profile instructs the iOS device to automatically trust the CA that the VPN server presents.

To create a trusted certificate profile:

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**. 
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **+ Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **Trusted certificate** for the **Profile type**.
4. Click the folder icon and browse to your VPN certificate (.cer file). Click **OK**.
5. Click **Create**.

    ![Create a trusted certificate profile](media\vpn-per-app-create-trusted-cert.png)

## Create a SCEP certificate profile

The trusted root certificate profile allows the iOS to automatically trust the VPN Server. The SCEP certificate provides credentials from the iOS VPN client to the VPN server. The certificate allows the device to silently authenticate without prompting the iOS devise user for a username and password. 

To create a SCEP certificate profile:

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**. 
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **+ Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **SCEP certificate** for the **Profile type**.
9. Select **Years** and type `1` for **Certificate validity period**.
10. Select **Common name as email** for **Subject name format**.
11. Select **Email address** and **User principle name (UPN)** for **Subject alternative name**.
12. Select **Digital signature** for **Key usage**.
13. Select **2048** for **Key size (bits)**.
14. Click Root Certificate and select a SCEP certificate. Click **OK**.
15. Type `Client Authentication` in **Name** for **Extended key usage**.
16. Type `1.3.6.1.5.5.7.3.2` in **Object Identifier**.
17. Click **Add**.
18. Type the **Server URL** and click **Add**.
19. Click **OK**.
20. Click **Create**.

    ![Create a SCEP certificate profile](media\vpn-per-app-create-SCEP-cert.png)

### Add an group assignment

## Create a Per-App VPN profile

The VPN profile contains the SCEP certificate carrying the client credentials, the connection information to the VPN, and the Per APP VPN flag to enable the Per App VPN feature for use by an application.

To create a Per-App VPN profile:

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

### Add an group assignment

## Associate an app with the VPN profile

Once you create a Per-App VPN profile, add a managed app to Intune. Select the app and click on Manage Deployments. Then click on the VPN Profile tab and you notice the VPN you created appears in the list for VPN Policy. `This section isn't right yet`.

To associate an app with the VPN profile:

1. Open the Azure portal. Choose **More Services** > **Monitoring + Management** > **Intune**.
2. Choose **Mobile Apps**.
3. Click **Apps**.
4. Click **+ Add** to add your app. For more information, see [Add your app](http://www.thelink.com).
5. Select the app from the list of apps.
6. Click **Assignments.**
7. Click **Select groups**, select a group, and click **Select**.
8. Select Required.
9. Select the VPN you defined in part three.

    ![Associate an app with the VPN](media\vpn-per-app-App-to-VPN.png)

### Add an group assignment

## Verify the connection on the iOS device

With your Per-App VPN set-up and associated with your app, verify the connection works from a device.

### Before you attempt to connect

 - Make sure you’re running iOS 7 or later
 - Make sure you deploy *all* of the above mentioned policies to the same group of users. Failure to do so will most definitely break the Per-App VPN experience  
 - Must have the appropriate third-party app installed, such as:
    - Juniper
    - Checkpoint
    - F5
    - SonicWall

### Connect using the Per-App VPN

Make sure you have a zero-touch experience by connecting without having to select the VPN or type your credentials. The zero-touch experience means:

 - The device does not ask you to trust the VPN server. That is, you do see the **Dynamic Trust** dialog box.
 - You do not have to type credentials.
 - You are connected to the VPN after tapping the connect button.

To verify the connection on an iOS device:

1. Tap on the VPN app.
2. Tap on **Connect**.  
The VPN successfully connects without any extra prompts.

## Troubleshooting the Per-App VPN

The user experiences the feature by seamlessly connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs.

## Next steps

To review iOS settings, see [VPN settings for iOS devices in Microsoft Intune](vpn-settings-ios.md).  
To learn more about VPN setting and Intune, see [How to configure VPN settings in Microsoft Intune](vpn-settings-configure.md).