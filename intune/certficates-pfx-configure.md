---
title: Use PKCS certificates with Microsoft Intune - Azure | Micrososft Docs
description: Add or create Public Key Cryptography Standards certificates with Microsoft Intune, including the steps to export a root certificate, configure the certificate template, download and install the Microsoft Intune Certificate Connector (NDES), create a device configuration profile, create a PKCS Certificate profile in Azure and your Certificate Authority.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure


---
# Configure and use PKCS certificates with Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certificates are used to authenticate and secure access to your corporate resources, such as a VPN or your WiFi network. This article shows you how to export a PKCS certificate, and then add the certificate to an Intune profile. 

## Requirements

To use PKCS certificates with Intune, be sure you have the following infrastructure:

- **Active Directory domain**: All servers listed in this section must be joined to your Active Directory domain.

  For more information about installing and configuring AD DS, see [AD DS Design and Planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Certification Authority** (CA): An Enterprise Certification Authority (CA)

  For more information on installing and configuring Active Directory Certificate Services (AD CS), see [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune requires you to run AD CS with an Enterprise Certification Authority (CA), not a Standalone CA.

- **A client**: To connect to the Enterprise CA

- **Root certificate**: An exported copy of your root certificate from your Enterprise CA

- **Microsoft Intune Certificate Connector**: Use the Azure portal to download the **Certificate Connector** installer (**NDESConnectorSetup.exe**). 

  The NDES Certificate connector also supports Federal Information Processing Standard (FIPS) mode. FIPS is not required, but you can issue and revoke certificates when it's enabled.

- **Windows Server**: Hosts the Microsoft Intune Certificate Connector (NDESConnectorSetup.exe)

## Export the root certificate from the Enterprise CA

To authenticate with VPN, WiFi, and other resources, a root, or intermediate CA certificate is needed on each device. The following steps explain how to get the required certificate from your Enterprise CA.

1. Sign in to your Enterprise CA with an account that has administrative privileges.
2. Open a command prompt as an administrator.
3. Export the Root CA Certificate (.cer) to a location where you can access it later.

   For example:

4. After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.

   `certutil -ca.cert certnew.cer`

   For more information, see [Certutil tasks for managing certificates](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## Configure certificate templates on the certification authority

1. Sign in to your Enterprise CA with an account that has administrative privileges.
2. Open the **Certification Authority** console, right-click **Certificate Templates**, and select **Manage**.
3. Locate the **User** certificate template, right-click it, and choose **Duplicate Template**. **Properties of New Template** opens.
4. On the **Compatibility** tab:

  - Set **Certification Authority** to **Windows Server 2008 R2**
  - Set **Certificate recipient** to **Windows 7 / Server 2008 R2**

5. On the **General** tab, set **Template display name** to something meaningful to you.

   > [!WARNING]
   > **Template name** by default is the same as **Template display name** with *no spaces*. Note the template name, you need it later.

6. In **Request Handling**, select **Allow private key to be exported**.
7. In **Cryptography**, confirm that the **Minimum key size** is set to 2048.
8. In **Subject Name**, choose **Supply in the request**.
9. In **Extensions**, confirm that you see Encrypting File System, Secure Email, and Client Authentication under **Application Policies**.

    > [!IMPORTANT]
    > For iOS certificate templates, go to the **Extensions** tab, update **Key Usage**, and confirm that **Signature is proof of origin** isn't selected.

10. In **Security**, add the Computer Account for the server where you install the Microsoft Intune Certificate Connector. Allow this account **Read** and **Enroll** permissions.
11. Select **Apply**, then **OK** to save the certificate template.
12. Close the **Certificate Templates Console**.
13. From the **Certification Authority** console, right-click **Certificate Templates**, **New**, **Certificate Template to Issue**. Choose the template that you created in the previous steps, and select **OK**.
14. For the server to manage certificates on behalf of Intune enrolled devices and users, follow these steps:

    1. Right-click the Certification Authority, choose **Properties**.
    2. On the security tab, add the Computer account of the server where you run the Microsoft Intune Certificate Connector. Grant **Issue and Manage Certificates** and **Request Certificates** Allow permissions to the computer account.

15. Sign out of the Enterprise CA.

## Download, install, and configure the certificate connector

![ConnectorDownload][ConnectorDownload]

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device configuration**, and then select **Certification Authority**.
4. Select **Add**, and **Download the Connector file**. Save the download to a location where you can access it from the server where you're going to install it.
5. After the download completes, sign in to the server. Then:

    1. Be sure .NET 4.5 Framework is installed, as it's required by the NDES Certificate connector. .NET 4.5 Framework is automatically included with Windows Server 2012 R2 and newer versions.
    2. Run the installer (NDESConnectorSetup.exe), and accept the default location. It installs the connector to `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`. In Installer Options, select **PFX Distribution**. Continue and complete the installation.

6. The NDES Connector opens the **Enrollment** tab. To enable the connection to Intune, **Sign In**, and enter an account with global administrative permissions.
7. On the **Advanced** tab, leave **Use this computer's SYSTEM account (default)** selected.
8. **Apply**, and then **Close**.
9. Go back to the Azure portal (**Intune** > **Device Configuration** > **Certification Authority**). After a few moments, a green check mark displays, and the **Connection status** is **Active**. Your connector server can now communicate with Intune.

> [!NOTE]
> TLS 1.2 support is included with the NDES Certificate connector. So if the server with NDES Certificate connector installed supports TLS 1.2, then TLS 1.2 is used. If the server doesn't support TLS 1.2, then TLS 1.1 is used. Currently, TLS 1.1 is used for authentication between the devices and server.

## Create a device configuration profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Go to **Intune** > **Device configuration** > **Profiles** > **Create profile**.

   ![NavigateIntune][NavigateIntune]

3. Enter the following properties:

  - **Name** for the profile
  - Optionally set a description
  - **Platform** to deploy the profile to
  - Set **Profile type** to **Trusted certificate**

4. Go to **Settings**, and enter the .cer file Root CA Certificate you previously exported.

   > [!NOTE]
   > Depending on the platform you chose in **Step 3**, you may or may not have an option to choose the **Destination store** for the certificate.

   ![ProfileSettings][ProfileSettings]

5. Select **OK**, and then **Create** to save your profile.
6. To assign the new profile to one or more devices, see [assign Microsoft Intune device profiles](device-profile-assign.md).

## Create a PKCS Certificate profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Go to **Intune** > **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

  - **Name** for the profile
  - Optionally set a description
  - **Platform** to deploy the profile to
  - Set **Profile type** to **PKCS Certificate**

4. Go to **Settings**, and enter the following properties:

  - **Renewal threshold (%)** - Recommended is 20%.
  - **Certificate validity period** - If you didn't change the certificate template, this option may be set to one year.
  - **Certification authority** - Displays the internal fully qualified domain name (FQDN) of your Enterprise CA.
  - **Certification authority name** - Lists the name of your Enterprise CA, and it may be different than the previous item.
  - **Certificate template name** - The name of the template created earlier. Remember **Template name** by default is the same as **Template display name** with *no spaces*.
  - **Subject name format** - Set this option to **Common name** unless otherwise required.
  - **Subject alternative name** - Set this option to **User principal name (UPN)** unless otherwise required.
  - **Extended key usage** - As long as you used the default settings in Step 10 in the [Configure certificate templates on the certification authority](#configure-certificate-templates-on-the-certification-authority) section (in this article), add the following **Predefined values** from the selection:
    - **Any Purpose**
    - **Client Authentication**
    - **Secure Email**
  - **Root Certificate** - (For Android Profiles) Lists the .cer file exported in Step 3 in the [Export the root certificate from the Enterprise CA](#export-the-root-certificate-from-the-enterprise-ca) section (in this article).

5. Select **OK**, then **Create** to save your profile.
6. To assign the new profile to one or more devices, see [assign Microsoft Intune device profiles](device-profile-assign.md).

## Next steps
[Use SCEP certificates](certificates-scep-configure.md), or [issue PKCS certificates from a Symantec PKI manager web wervice](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigate to Intune in the Azure portal and create a new profile for a trusted certificate"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Create a profile and upload a trusted certificate"
[ConnectorDownload]: ./media/certificates-download-connector.png "Download the certificate connector from the Azure portal"  
