---
title: Configure and manage PKCS certificates with Intune
titleSuffix: "Intune on Azure"
description: Create and assign PKCS certificates with Intune."
keywords:
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 11/16/2017
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
# Configure and manage PKCS certificates with Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## Requirements

To use PKCS certificates with Intune, you must have the following infrastructure:

* An existing Active Directory Domain Services (AD DS) domain configured.
 
  If you need more information about how to install and configure AD DS see the article [AD DS Design and Planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* An existing Enterprise Certification Authority (CA) configured.

  If you need more information about how to install and configure Active Directory Certificate Services (AD CS) see the article [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune requires you to run AD CS with an Enterprise Certification Authority (CA), not a Standalone CA.

* A client that has connectivity to the Enterprise CA.
* An exported copy of your root certificate from your Enterprise CA.
* The Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) downloaded from your Intune Portal.
* A Windows Server available to host the Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## Export the root certificate from the Enterprise CA

You need a root or intermediate CA certificate on each device for authentication with VPN, WiFi, and other resources. The following steps explain how to get the required certificate from your Enterprise CA.

1. Log in to your Enterprise CA with an account that has administrative privileges.
2. Open a command prompt as an administrator.
3. Export the Root CA Certificate to a location where you can access it later.

   For example:

   `certutil -ca.cert certnew.cer`

   For more information, see [Certutil tasks for managing certificates](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## Configure certificate templates on the certification authority

1. Log in to your Enterprise CA with an account that has administrative privileges.
2. Open the **Certification Authority** console.
3. Right-click **Certificate Templates** and choose **Manage**.
4. Locate the **User** certificate template, right-click it and choose **Duplicate Template**. A window opens, **Properties of New Template**.
5. On the **Compatibility** tab
   * Set **Certification Authority** to **Windows Server 2008 R2**
   * Set **Certificate recipient** to **Windows 7 / Server 2008 R2**
6. On the **General** tab:
   * Set **Template display name** to something meaningful to you.

   > [!WARNING]
   > **Template name** by default is the same as **Template display name** with *no spaces*. Note the template name for later use.

7. On the **Request Handling** tab, check the **Allow private key to be exported** box.
8. On the **Cryptography** tab, confirm that the **Minimum key size** is set to 2048.
9. On the **Subject Name** tab, choose the radio button **Supply in the request**.
10. On the **Extensions** tab, confirm that you see Encrypting File System, Secure Email, and Client Authentication under **Application Policies**.
    
      > [!IMPORTANT]
      > For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.

11. On the **Security** tab, add the Computer Account for the server where you install the Microsoft Intune Certificate Connector.
    * Allow this account **Read** and **Enroll** permissions.
12. Click **Apply**, then click **OK** to save the certificate template.
13. Close the **Certificate Templates Console**.
14. From the **Certification Authority** console, right-click **Certificate Templates**, **New**, **Certificate Template to Issue**.
    * Choose the template that you created in the preceding steps and click **OK**.
15. For the server to manage certificates on behalf of Intune enrolled devices and users, follow these steps:

    a. Right-click the Certification Authority, choose **Properties**.

    b. On the security tab, add the Computer account of the server where you run the Microsoft Intune Certificate Connector.
      * Grant **Issue and Manage Certificates** and **Request Certificates** Allow permissions to the computer account.
16. Log out of the Enterprise CA.

## Download install and configure the Microsoft Intune Certificate Connector

![ConnectorDownload][ConnectorDownload]

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Navigate to **Intune**, **Device configuration**, **Certification Authority**, and click **Download the certificate connector**.
   * Save the download to a location where you can access it on the server where you will install it.
3. Log in to the server where you will install the Microsoft Intune Certificate Connector.
4. Run the installer and accept the default location. It installs the connector to C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.

      a. On the Installer Options page chose **PFX Distribution** and click **Next**.

   b. Click **Install** and wait for installation to complete.

   c. On the completion page, check the box labeled **Launch Intune Connector** and click **Finish**.

5. The NDES Connector window should now open to the **Enrollment** tab. To enable the connection to Intune, you must click **Sign In** and provide an account with administrative permissions.
6. On the **Advanced** tab, you can leave the radio button **Use this computer's SYSTEM account (default)** selected.
7. Click **Apply** then **Close**.
8. Now go back on the Azure portal. Under **Intune**, **Device configuration**, **Certification Authority**, you should see a green check mark and the word **Active** under **Connection status** after a few minutes. This confirmation lets you know that your connector server can communicate with Intune.

## Create a device configuration profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.

   ![NavigateIntune][NavigateIntune]

3. Populate the following information:
   * **Name** for the profile
   * Optionally set a description
   * **Platform** to deploy the profile to
   * Set **Profile type** to **Trusted certificate**
4. Navigate to **Settings** and provide the .cer file Root CA Certificate exported previously.

   > [!NOTE]
   > Depending on the Platform you chose in **Step 3** you may or may not have an option to choose the **Destination store** for the certificate.

   ![ProfileSettings][ProfileSettings]

5. Click **OK** then **Create** to save your profile.
6. To assign the new profile to one or more devices see [How to assign Microsoft Intune device profiles](device-profile-assign.md).

## Create a PKCS Certificate profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.
3. Populate the following information:
   * **Name** for the profile
   * Optionally set a description
   * **Platform** to deploy the profile to
   * Set **Profile type** to **PKCS Certificate**
4. Navigate to **Settings** and provide the following information:
   * **Renewal threshold (%)** - Recommended is 20%.
   * **Certificate validity period** - If you did not change the certificate template this option should be set to one year.
   * **Certification authority** - This option is the internal fully qualified domain name (FQDN) of your Enterprise CA.
   * **Certification authority name** - This option is the name of your Enterprise CA and may be different than the previous item.
   * **Certificate template name** - This option is the name of the template created earlier. Remember **Template name** by default is the same as **Template display name** with *no spaces*.
   * **Subject name format** - Set this option to **Common name** unless otherwise required.
   * **Subject alternative name** - Set this option to **User principal name (UPN)** unless otherwise required.
   * **Extended key usage** - As long as you used the default settings in step 10 in the preceding section **Configure certificate templates on the certification authority**, add the following **Predefined values** from the selection box:
      * **Any Purpose**
      * **Client Authentication**
      * **Secure Email**
   * **Root Certificate** - (For Android Profiles) This option is the .cer file exported in step 3 under the previous section [Export the root certificate from the Enterprise CA](#export-the-root-certificate-from-the-enterprise-ca).

5. Click **OK**, then click **Create** to save your profile.
6. To assign the new profile to one or more devices, see the article [How to assign Microsoft Intune device profiles](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigate to Intune in the Azure portal and create a new profile for a trusted certificate"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Create a profile and upload a trusted certificate"
[ConnectorDownload]: ./media/certificates-pfx-configure-connector-download.png "Download the certificate connector from the Azure portal"
