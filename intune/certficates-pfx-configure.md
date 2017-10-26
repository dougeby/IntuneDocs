---
title: Configure and manage PKCS certificates with Intune
titlesuffix: "Azure portal"
description: Learn how to configure your infrastructure, then create and assign PKCS certificates with Intune."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: vinaybha
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure


---
# Configure and manage PKCS certificates with Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic shows how to configure your infrastructure, then create and assign PKCS certificate profiles with Intune.

To do any certificate-based authentication in your organization, you need an Enterprise Certification Authority.

To use PKCS Certificate profiles, in addition to the Enterprise Certification Authority, you also need:

-   A computer that can communicate with the Certification Authority, or you can use the Certification Authority computer itself.

-  The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.

## Important terms


-    **Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.

-  **Certification Authority**: An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later. A Standalone CA is not supported. For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).
    If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Computer that can communicate with Certification Authority**: Alternatively, use the Certification Authority computer itself.
-  **Microsoft Intune Certificate Connector**: From the Azure portal, you download the **Certificate Connector** installer (**ndesconnectorssetup.exe**). Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector. For PKCS Certificate profiles, install the Certificate Connector on the computer that communicates with the Certification Authority.
-  **Web Application Proxy server** (optional): You can use a server that runs Windows Server 2012 R2 or later as a Web Application Proxy (WAP) server. This configuration:
    -  Allows devices to receive certificates using an Internet connection.
    -  Is a security recommendation when devices connect through the Internet to receive and renew certificates.

 > [!NOTE]           
> -    The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service (NDES). This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Also, the server that hosts WAP must have an SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server. These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.
    For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx). For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|


## Certificates and templates

|Object|Details|
|----------|-----------|
|**Certificate Template**|You configure this template on your issuing CA.|
|**Trusted Root CA certificate**|You export this as a **.cer** file from the issuing CA or any device which trusts the issuing CA, and assign it to devices by using the Trusted CA certificate profile.<br /><br />You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.<br /><br />You can use additional Trusted Root CA certificates when needed. For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.|


## Configure your infrastructure
Before you can configure certificate profiles, you must complete the following steps. These steps require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):

- **Step 1** - Configure certificate templates on the certification authority.
- **Step 2** - Enable, install, and configure the Intune Certificate Connector.

## Step 1 - Configure certificate templates on the certification authority

### To configure the certification authority

1.  On the issuing CA, use the Certificate Templates snap-in to create a new custom template, or copy and edit an existing template (like the User template), for use with PKCS.

    The template must include the following:

    -   Specify a friendly **Template display name** for the template.

    -   On the **Subject Name** tab, select **Supply in the request**. (Security is enforced by the Intune policy module for NDES).

    -   On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.

        > [!IMPORTANT]
        > For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.

2.  Review the **Validity period** on the **General** tab of the template. By default, Intune uses the value configured in the template. However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console. If you want to always use the value in the template, skip the remainder of this step.

    > [!IMPORTANT]
    > iOS and macOS always use the value set in the template, regardless of other configurations you make.

    To configure the CA to allow the requester to specify the validity period, run the following commands on the CA:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  On the issuing CA, use the Certification Authority snap-in to publish the certificate template.

    a.  Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.

    b.  Validate that the template published by viewing it under the **Certificate Templates** folder.

4.  On the CA computer, ensure that the computer that hosts the Intune Certificate Connector has enroll permission, so that it can access the template used in creating the PKCS certificate profile. Set that permission on the **Security** tab of the CA computer properties.

## Step 2 - Enable, install, and configure the Intune certificate connector
In this step you will:

- Enable support for the Certificate Connector
- Download, install, and configure the Certificate Connector.

### To enable support for the certificate connector

1.  Sign into the Azure portal.
2.  Choose **More Services** > **Monitoring + Management** > **Intune**.
3.  On the **Intune** blade, choose **Configure devices**.
2.  On the **Device Configuration** blade, choose **Setup** > **Certificate Authority**.
2.  Under **Step 1**, choose **Enable**.

### To download, install, and configure the certificate connector

1.  On the **Configure devices** blade, choose **Setup** > **Certificate Authority**.
2.  choose **Download the certificate connector**.
2.  After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**).
  Run the installer on the computer that is able to connect with the Certification Authority. Choose the PKCS (PFX) Distribution option, and then choose **Install**. When the installation has completed, continue by creating a certificate profile as described in [How to configure certificate profiles](certificates-configure.md).

4.  After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.

    > [!TIP]
    > If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In the **Certificate Connector** UI:

    a. Choose **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority.

    c. Choose **Apply**.

    You can now close the Certificate Connector UI.

6.  Open a command prompt and type **services.msc**. Then press **Enter**, right-click the **Intune Connector Service**, and choose **Restart**.

To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**


### How to create a PKCS certificate profile

In the Azure Portal, select the **Configure devices** workload.
2. On the **Device configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the PKCS certificate profile.
5. From the **Platform** drop-down list, select the device platform for this PKCS certificate from:
	- **Android**
	- **Android for Work**
	- **iOS**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **PKCS certificate**.
7. On the **PKCS Certificate** blade, configure the following settings:
	- **Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.
	- **Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.<br>You can specify a value that is lower than the validity period in the specified certificate template, but not higher. For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years. The value must also be lower than the remaining validity period of the issuing CA's certificate.
	- **Key storage provider (KSP)** (Windows 10) - Specify where the key to the certificate will be stored. Choose from one of the following values:
		- **Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**
		- **Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**
		- **Enroll to Passport, otherwise fail (Windows 10 and later)**
		- **Enroll to Software KSP**
	- **Certification authority** - An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later. A Standalone CA is not supported. For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx). If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).
	- **Certification authority name** - Enter the name of your certification authority.
	- **Certificate template name** - Enter the name of a certificate template that the Network Device Enrollment Service is configured to use and that has been added to an issuing CA.
	Make sure that the name exactly matches one of the certificate templates that are listed in the registry of the server that is running the Network Device Enrollment Service. Make sure that you specify the name of the certificate template and not the display name of the certificate template. 
	To find the names of certificate templates, browse to the following key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. You will see the certificate templates listed as the values for **EncryptionTemplate**, **GeneralPurposeTemplate**, and **SignatureTemplate**. By default, the value for all three certificate templates is IPSECIntermediateOffline, which maps to the template display name of **IPSec (Offline request)**. 
	- **Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request. If the certificate is for a user, you can also include the user's email address in the subject name. Choose from:
		- **Not configured**
		- **Common name**
		- **Common name including email**
		- **Common name as email**
	- **Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request. For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name. If the client certificate is used to authenticate to a Network Policy Server, set the subject alternative name to the UPN. 
	You can also select **Custom Azure AD attribute**. When you select this option, another drop-down field is displayed. From the **Custom Azure AD attribute** drop-down field, there is one option: **Department**. When you select this option, if the department is not identified in Azure AD, the certificate is not issued. To resolve this issue, identify the department and save the changes. At the next device checkin, the problem is resolved and certificate is issued. ASN.1 is the notation used for this field. 
	- **Extended key usage** (Android) - Choose **Add** to add values for the certificate's intended purpose. In most cases, the certificate will require **Client Authentication** so that the user or device can authenticate to a server. However, you can add any other key usages as required. 
	- **Root Certificate** (Android) - Choose a root CA certificate profile that you have previously configured and assigned to the user or device. This CA certificate must be the root certificate for the CA that will issue the certificate that you are configuring in this certificate profile. This is the trusted certificate profile that you created previously.
8. When you're done, go back to the **Create Profile** blade, and click **Create**.

The profile is created and is displayed on the profiles list blade.

## How to assign the certificate profile

Consider the following before you assign certificate profiles to groups:

- When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device. The device uses the PKCS certificate profile to create a certificate request by the device.
- Certificate profiles install only on devices running the platform you use when you created the profile.
- You can assign certificate profiles to user collections or to device collections.
- To publish a certificate to a device quickly after the device enrolls, assign the certificate profile to a user group rather than to a device group. If you assign to a device group, a full device registration is required before the device receives policies.
- Although you assign each profile separately, you also need to assign the Trusted Root CA and the PKCS profile. Otherwise, the PKCS certificate policy will fail.

For information about how to assign profiles, see [How to assign device profiles](device-profile-assign.md).
