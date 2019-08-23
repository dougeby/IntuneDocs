---
title: Use private and public key certificates in Microsoft Intune - Azure | Microsoft Docs
description: Add Imported Public Key Cryptography Standards (PKCS) certificates with Microsoft Intune, including the steps import the certificates, configure the certificate template, download, and install the Intune Imported PFX Certificate Connector and create an Imported PKCS Certificate profile in Azure.
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

With Email profiles in Intune there is the option to enable S/MIME where you can define an S/MINE Signing Cert and S/MINE Encryption Cert.
For more information regarding using S/MINE with Intune, [Use S/MIME to encrypt email](certificates-s-mime-encryption-sign.md).

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

- **Visual Studio 2015 or above** (optional): Required to build the helper Powershell module with cmdlets for importing PFX certificates to Microsoft Intune that is provided at [PFXImport Powershell Project in GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)

## How it works

When deploying an **Imported PFX certificate** to a user device via Intune, other than the device itself there are 2 components at play:

- **Intune Service**: Stores the PFX certificates in an encrypted state and handles the deployment of the certificate to the user device.
- **Imported PFX Certificate Connector**: Decrypts the PFX certificates using a local key.

Whenever a user targeted by a **PFX Imported Certificate profile** in Intune, Intune will start by looking if there is any certificate for that user imported with Graph. If yes, will request the **Imported PFX Certificate connector** to decrypt that certificate, where after that the certificate is pushed to the device by Intune.

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

## Importing the PFX Certificates to Intune

Although the action of importing your users PFX certificates to Intune is achieved with [Microsoft Graph](https://docs.microsoft.com/en-us/graph), the helper [PFXImport Powershell Project at GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) provides you with cmdlets to perform the operations easily.

If you prefer to implement a custom solution yourself using Graph, the [userPFXCertificate resource type](https://docs.microsoft.com/en-us/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta) is used.

### Build 'PFXImport Powershell Project' cmdlets

To take advantage of these cmdlets, you will be required to build the project yourself using Visual Studio unfortunately, however the process is fairly straight forward.

> [!NOTE]
> The following process is not required to be performed on the server, your normal workstation machine is recommended.

1. At the root of [Intune-Resource-Access](https://github.com/microsoft/Intune-Resource-Access) repository, either download or clone it with Git to your machine.

    ![GitHub download button](media/certificates-importedpfx-configure/github-download.png)

2. Go to `.\Intune-Resource-Access-develop\src\PFXImportPowershell\` and open the project with Visual Studio using the file **PFXImportPS.sln**.
3. On the top, change from **Debug** to **Release**.
4. Go to **Build** and select **Build PFXImportPS**, after a few seconds at the bottom left of Visual Studio you will have a **Build succeeded** confirmation.

    ![Visual Studio Build option](media/certificates-importedpfx-configure/vs-build-release.png)

5. A new folder is created with the Powershell Module at `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release`.

    You will need this **Release** folder for the next steps.

### Creating encryption Public Key

PFX Certificates are imported to Intune encrypted, as such a public key is required. This key is managed and kept by the administrator installed on the server where it was created and additionally also saved file format for backup purposes.

Although the Powershell module provides methods to create a key, other tools can be used.

To start, please copy the folder with Powershell module generated from Visual Studio to the server itself where the **Imported PFX Certificate Connector** is installed.

1. On the server, open Powershell as Administrator and navigate to where the folder with the Powershell module is located.
2. Import the module with `Import-Module .\IntunePfxImport.psd1`
3. Run `Add-IntuneKspKey "Microsoft Software Key Storage Provider" "PFXEncryptionKey"`

    Other provider and key name can be used.

    Also, if you will be importing the certificate at your workstation, you can export this key to a file with:
    `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path to write to>"`

> [!NOTE]
> The same key can be used for multiple PFX certificates, even if from different users.

### Importing PFX Certificates using the Powershell cmdlets

The following process will be an example on how to import the PFX certificates, however you can pick different options depending on your requirements.

For reference here is the list of the possible options:

     - Intended Purpose:

        0. unassigned
        1. smimeEncryption
        2. smimeSigning

     - Padding Scheme:

        1. pkcs1
        2. oaepSha1
        3. oaepSha256
        4. oaepSha384
        5. oaepSha512

Additionally, you will have to decide what Key Storage Provider to use, we recommend **Microsoft Software Key Storage Provider** and a name for your key. This Key Storage Provider needs to match the one used when creating the key on the server.

With the folder generated from Visual Studio with the cmdlets, in order to import the PFX certificate perform the following:

1. Open Powershell as Administrator and navigate to where the folder with the Powershell module is located.
2. Import the module with `Import-Module .\IntunePfxImport.psd1`
3. Authenticate to Intune Graph with `$authResult = Get-IntuneAuthenticationToken -AdminUserName "<Admin-UPN>"`

    > [!NOTE]
        > As the authentication is against Graph, permissions to the AppID need to be provided.
        > If it's the first time using this utility, a Global administrator is required to concent those permissions.
        > These Powershell cmdlets are using the same AppID as the one used with [Powershell Intune Samples](https://github.com/microsoftgraph/powershell-intune-samples) as such more permissions than it actually be used will be requested.

4. Save the PFX password used when the exporting the certificate to a variable with `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force`
5. Create a **UserPFXCertificate** object with
`$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>"`

    E.g.: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption" "pkcs1"`

    > [!NOTE]
        > In order to import the certificate from your Workstation and not the server, the key file path needs to be specified on the previous mentioned command.
        > `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

6. Import the **UserPFXCertificate** object to Intune by running `Import-IntuneUserPfxCertificate -AuthenticationResult $authResult -CertificateList $userPFXObject`

7. Validate the certificate was imported with `Get-IntuneUserPfxCertificate -AuthenticationResult $authResult -UsertList "<UserUPN>"`

More information of other available commands can be found at the read me from [PFXImport Powershell Project at GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)

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

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md) to your email configuration policy and [monitor its status](device-profile-monitor.md).

