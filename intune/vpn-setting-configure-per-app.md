---
# required metadata

title: Set up per-app VPN for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: See the prerequisites, create a group for the virtual private network (VPN) users, add a SCEP certificate profile, configure a per-app VPN profile, and assign some apps to the VPN profile in Microsoft Intune on iOS devices. Also lists the steps to verify the VPN connection on the device.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/31/2019
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
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up per-app Virtual Private Network (VPN) in Intune for iOS devices

You can specify which managed apps can use your Virtual Private Network (VPN) on iOS devices managed by Intune. When you create a per-app VPN in Intune, a user automatically connects through your VPN when accessing corporate documents.

Check your VPN provider's documentation to see if your VPN supports per-app VPN.

The following instructions will help you create a seamless per-app VPN experience. For most VPNs that support per-app VPN, this means the user only needs to open one of the associated apps to connect to the VPN.

Some VPNs allow username and password authentication with per-app VPN; however, this experience isn't seamless because users need to enter a username and password to connect to the VPN.

## Per-app VPN with Zscaler

Zcaler Private Access (ZPA) integrates with Azure Active Directory (Azure AD) for authentication. As a result, you can skip the certificate profile instructions below if you're using ZPA. If you have a per-app VPN profile set up for Zscaler, opening one of the associated apps doesn't automatically connect to ZPA; instead, the user needs to sign into the Zscaler app first, and remote access will be limited to the associated apps.

## Prerequisites for per-app VPN

> [!IMPORTANT]
> Your VPN vendor may have other specific requirements for per-app VPN, such as specific hardware or licensing. Be sure to check with their documentation, and meet those prerequisites before setting up per-app VPN in Intune.

To prove its identity, the VPN server presents the certificate that must be accepted without a prompt by the device. To ensure the automatic approval of the certificate, create a trusted certificate profile that contains the VPN server's root certificate issued by the Certification Authority (CA). 

Export the certificate and add the CA.

1. Open the administration console on your VPN server.
2. Verify that your VPN server uses certificate-based authentication. 
3. Export the trusted root certificate file. It has a .cer extension, and you add it when creating a trusted certificate profile.
4. Add the name of the CA that issued the certificate for authentication to the VPN server.
    If the CA presented by the device matches one of the CAs in the Trusted CA list on the VPN server, then the VPN server successfully authenticates the device.

## Create a group for your VPN users

Create or choose an existing group in Azure Active Directory (Azure AD) for the users or devices that will use per-app VPN.

To create a new group, see [Add groups to organize users and devices](groups-add.md).

## Create a trusted certificate profile

Import the VPN server's root certificate issued by the CA into a profile created in Intune. The trusted certificate profile instructs the iOS device to automatically trust the CA that the VPN server presents.

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **Trusted certificate** for the **Profile type**.
4. Click the folder icon and browse to your VPN certificate (.cer file) that you exported from your VPN administration console. Click **OK**.
5. Click **Create**.

    ![Create a trusted certificate profile](./media/vpn-per-app-create-trusted-cert.png)

## Create a SCEP or PKCS certificate profile

The trusted root certificate profile allows the iOS to automatically trust the VPN Server. The SCEP or PKCS certificate provides credentials from the iOS VPN client to the VPN server. The certificate allows the device to silently authenticate without prompting the iOS device user for a username and password. 

See one of the following topics for help configuring and assigning the client authentication certificate:

- [Configure and manage SCEP certificates with Intune](certificates-scep-configure.md)
- [Configure and manage PKCS certificates with Intune](certficates-pfx-configure.md)

Be sure to configure the certificate for client authentication. You can set this directly in SCEP certificate profiles by choosing **Client authentication** in the **Extended key usage** list. For PKCS, you need set this in the certificate template in the CA.

    ![Create a SCEP certificate profile](./media/vpn-per-app-create-scep-cert.png)

## Create a per-app VPN profile

The VPN profile contains the SCEP certificate carrying the client credentials, the connection information to the VPN, and the per-app VPN flag to enable the per-app VPN feature for use by the iOS application.

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Choose **Device configuration**, and then click **Profiles**.
3. Click **Create profile**. In **Create profile**:
    1. Type the **Name**.
    2. Type the **Description**.
    3. Select **iOS** for the **Platform**.
    4. Select **VPN** for the **Profile type**.
4. Select your VPN client app for the **Connection type**.
4. Select **Base VPN**. In **Base VPN**:
    1. Type the **Connection name**.
    2. Type the **IP address or FQDN**.
    3. Select **Certificates** for the **Authentication method**.
    4. Select the SCEP or PKCS certificate you created earlier under **Authentication certificate** and click **OK**.
    5. If necessary, configure the attributes for your VPN.
    6. Set **Split tunneling** to **Disable**.
5. Click **Automatic VPN**. In **Automatic VPN**:
    1. Select **Per-app VPN** for the **Type of automatic VPN**.
    2. Click **OK**.
6. Click **OK**.
7. Click **Create**.

    ![Create a per-app VPN profile](./media/vpn-per-app-create-vpn-profile.png)


## Associate an app with the VPN profile

After adding your VPN profile, associate the app and Azure AD group to the profile.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Choose **Client apps**.
4. Click **Apps**.
5. Select the app from the list.
6. Click **Assignments**.
7. Click **Add group**.
8. Select either **Required** or **Available for enrolled devices** for the **Assignment type**.
9. Select the group you defined earlier and click **Select**.
10. Select the per-app VPN profile you created earlier from the **VPNs** menu.
11. Click **OK** and click **Save**.

    ![Associate an app with the VPN](./media/vpn-per-app-app-to-vpn.png)

An association between an app and a profile will be removed during the next device check-in, when all of the following conditions exist:
- The app was targeted with required install intent.
- Both the profile and the app are targeted to the same group.
- You remove the per-app VPN configuration from the app assignment.

An association between an app and a profile will persist until the user requests a reinstall from Company Portal, when all of the following conditions exist:
- The app was targeted with available install intent.
- Both the profile and the app are targeted to the same group.
- The end user requested app install from Company Portal, which results in app and profile being installed on the device.
- You remove or change the per-app VPN configuration from the app assignment.

## Verify the connection on the iOS device

With your per-app VPN set-up and associated with your app, verify the connection works from a device.

### Before you attempt to connect

 - Make sure you deploy all of the above mentioned policies to the same group; otherwise the per-app VPN experience won't work.
 - If you're using the Pulse Secure VPN app or a custom VPN client app, you can choose to use app-layer or packet-layer tunneling. Set the **ProviderType** value to **app-proxy** for app-layer tunneling or **packet-tunnel** for packet-layer tunneling. Check your VPN provider's documentation to make sure you're using the right value.

### Connect using the per-app VPN

Verify the zero-touch experience by connecting without having to select the VPN or type your credentials. The zero-touch experience means:

 - The device doesn't ask you to trust the VPN server. That is, the user doesn't see the **Dynamic Trust** dialog box.
 - The user doesn't have to type credentials.
 - The user's device is connected to the VPN when the user opens one of the associated apps.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## Next steps

- To review iOS settings, see [VPN settings for iOS devices in Microsoft Intune](vpn-settings-ios.md).
-  To learn more about VPN setting and Intune, see [How to configure VPN settings in Microsoft Intune](vpn-settings-configure.md).
