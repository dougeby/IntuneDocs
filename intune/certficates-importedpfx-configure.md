---
title: Use private and public key certificates in Microsoft Intune - Azure | Microsoft Docs
description: Add or create Public Key Cryptography Standards (PKCS) certificates with Microsoft Intune, including the steps to export a root certificate, configure the certificate template, download, and install the Intune Certificate Connector (NDES), create a device configuration profile, and create a PKCS Certificate profile in Azure and your Certificate Authority.
keywords:
author: rimarram
ms.author: rimarram
manager: elstoene
ms.date: 08/22/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; seodec18

ms.collection: M365-identity-device-management
---
# Configure and use Imported PKCS certificates with Intune

With Email profiles in Intune there is the option to enable S/MIME where you can define a S/MINE Signing Cert and S/MINE Encryption Cert.
For more information in regards to using S/MINE with Intune, [Use S/MIME to encrypt email](certificates-s-mime-encryption-sign.md).

The challenge is with handling the S/MINE Encryption certificates, since revoking or deleting such certificate would result on loosing the email contents it encrypted.
As such, it's not possible to use the normal [SCEP](certificates-scep-configure.md) or [PKCS](certficates-pfx-configure.md) profiles for this purpose, as when the device is unenrolled, the certificates issues with those profiles are revoked.

## Requirements

To use Imported PKCS certificates with Intune, you'll need the following infrastructure:

- **PFX Certificate Connector for Microsoft Intune**:  
   In the Intune portal, go to **Device configuration** > **Certificate Connectors** > **Add**, and follow the *Steps to install connector for Imported PFX certificates*. Use the download link in the portal to start download of the installer **PfxCertificateConnectorBootstrapper.exe**.

  This connector handles requests for PFX files imported to Intune for S/MIME email encryption for a specific user.  

  This connector can automatically update itself when new versions become available. To use the update capability, you must:
  - Install the Imported PFX Certificate Connector for Microsoft Intune on your server.
  - To automatically receive important updates, ensure firewalls are open that allow the connector to contact **autoupdate.msappproxy.net** on port **443**.  

- **Windows Server**:  
  You use a Windows Server to host:

  - Imported PFX Certificate Connector for Microsoft Intune - for S/MIME email signing or encryption scenarios.

  You can install both connectors (*Microsoft Intune Certificate Connector* and *Imported PFX Certificate Connector*) on the same server.

## How it works

TODO

## Importing the PFX Certificates to Intune

TODO

## Download, install, and configure the Imported PFX Certificate Connector for Microsoft Intune

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Certification Connectors** > **Add**

    ![Imported PFX connector download](media/certificates-importedpfx-configure/download-importedPFXConnector.png)

3. Download and save the Imported PFX Certificate Connector for Microsoft Intune. Save it to a location accessible from the server where you're going to install the connector.
4. After the download completes, sign in to the server. Then:

    1. Be sure .NET 4.6 Framework or higher is installed, as it's required by the Imported PFX Certificate Connector for Microsoft Intune. If .NET 4.6 Framework isn't installed, the installer installs it automatically.
    2. Run the installer (PfxCertificateConnectorBootstrapper.exe), and accept the default location, which installs the connector to `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. The connector service runs under the local system account. If a proxy is required for internet access, then confirm that the local service account can access the proxy settings on the server.

5. The PFX Certificate Connector for Microsoft Intune opens the **Enrollment** tab after installation. To enable the connection to Intune, **Sign In**, and enter an account with Azure global administrator or Intune administrator permissions.

    > [!WARNING]
        > In Windows Server, **IE Enhanced Security Configuration** by default is set to **On**, this can cause issues with the login to Office 365.

6. Close the window.
7. Go back to the Azure portal (**Intune** > **Device Configuration** > **Certification Connectors**). After a few moments, a green check mark is shown, and the **Connection status** is **Active**. Your connector server can now communicate with Intune.

## Create a PKCS imported certificate profile

You can import certificates previously issued to a specific user from any CA in to Intune. Imported certificates are installed on each device that a user enrolls. S/MIME email encryption is the most common scenario for importing existing PFX certificates in to Intune. A user may have many certificates to encrypt email. The private keys of those certificates must exist on all of a user's devices so they can decrypt previously encrypted email.

To import certificates into Intune, you can use the [PowerShell cmdlets provided on GitHub](https://github.com/Microsoft/Intune-Resource-Access).

After importing the certificates to Intune, create a **PKCS imported certificate** profile, and assign it to Azure Active Directory groups.

1. In the [Azure portal](https://portal.azure.com), go to **Intune** > **Device configuration** > **Profiles** > **Create profile**.
2. Enter the following properties:

    - **Name** for the profile
    - Optionally set a description
    - **Platform** to deploy the profile to
    - Set **Profile type** to **PKCS imported certificate**

3. Go to **Settings**, and enter the following properties:

    - **Intended purpose**: The intended purpose of the certificates that are imported for this profile. An administrator may have imported certificates with different intended purposes (such as authentication, S/MIME signing, or S/MIME encryption). The intended purpose selected in the certificate profile matches the certificate profile with the right imported certificates.
    - **Certificate validity period**: If you didn't change the certificate template, this option may be set to one year.
    - **Key storage provider (KSP)**: For Windows, select where to store the keys on the device.

4. Select **OK** > **Create** to save your profile.
5. To assign the new profile to one or more devices, see [assign Microsoft Intune device profiles](device-profile-assign.md).

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

[Use SCEP certificates](certificates-scep-configure.md), or [issue PKCS certificates from a Symantec PKI manager web service](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigate to Intune in the Azure portal and create a new profile for a trusted certificate"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Create a profile and upload a trusted certificate"
[ConnectorDownload]: ./media/certificates-download-connector.png "Download the certificate connector from the Azure portal"  
