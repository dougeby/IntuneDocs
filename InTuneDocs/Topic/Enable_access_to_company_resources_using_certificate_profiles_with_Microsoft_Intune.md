---
title: Enable access to company resources using certificate profiles with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
author: Nbigman
---
# Enable access to company resources using certificate profiles with Microsoft Intune
Certificate profiles are [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies that configure managed devices with the certificates they need so device users can connect to your on-premises company resources using connections like Wi-Fi or VPN. When you deploy certificate profiles, you provision devices with a trusted root certificate for your PKI, and configure them to request device specific certificates.

You can create three types of certificate profiles:

-   PKCS #12 (.PFX) Certificate Profile: this can be used with Android 4.0 or later and Windows 10 (desktop and mobile) and later.

-   SCEP Certificate Profile: this can be used with iOS 6.0 and later, Mac OS X 10.9 and later, Android 4.0 or later, and Windows Phone 8.1 and later.

-   Trusted Certificate Profile: this can be used with iOS 6.0 and later, Mac OS X 10.9 and later, Android 4.0 or later, and Windows Phone 8.1 and later.

|About certificate profiles|Details|
|------------------------------|-----------|
|Use certificate profiles to:|Automatically configure devices so that company resources can be accessed without having to install certificates manually or by using an out-of-band process<br /><br />Help to keep company resources secure by using your enterprise public key infrastructure (PKI)<br /><br />Enable you to use server authentication for all connections like Wi-Fi and VPN because you have provisioned the required certificates on the managed devices|
|Certificate profiles provide the following management capabilities:|Certificate enrollment and renewal from an Enterprise Certification Authority (CA) for devices that run: Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1.<br /><br />These certificates can then be used for connections to your on-premises infrastructure.<br /><br />Deployment of Trusted Root CA certificates and intermediate CA certificates to configure a chain-of-trust with devices for connections where server authentication is required.<br /><br />Monitor and report about the installed certificates.|
|Examples of when to use certificate profiles:|Employees must be able to connect to Wi-Fi hotspots in multiple corporate locations. To do this, you can use certificate profiles to deploy the certificates required to secure the Wi-Fi connection.<br /><br />You have a PKI in place and want to move to a more flexible, secure method of provisioning certificates that lets users access company resources from their personal devices without compromising security. To do this, you can configure certificate profiles with settings and protocols that are supported for the specific device platform. The devices can then automatically request these certificates from an Internet-facing enrollment server. You can then configure VPN profiles to use these certificates so that the device can access company resources.|

|Types  of certificate profiles|Details|
|----------------------------------|-----------|
|**Trusted Root Certificate profile**|Use this profile to deploy the Trusted Root CA certificate or intermediate CA certificate to devices:<br /><br />Create a Trusted Root Certificate profile for each platform you use. You will pair this with each SCEP certificate profile you create for that same platform.|
|**.PFX Certificate profile**|Use this profile to deploy platform specific settings for device certificate requests:<br /><br />Create a .PFX certificate profile for each platform you use, and pair it with the Trusted CA certificate profile.<br /><br />To complete the task of creating a .PFX certificate profile, you must select a previously created Trusted CA certificate profile.|
|**Simple Certificate Enrollment Protocol (SCEP) settings profile**|Use this profile to deploy platform specific settings for device certificate requests:<br /><br />Create a SCEP certificate profile for each platform you use, and pair it with the Trusted CA certificate profile.<br /><br />To complete the task of creating a SCEP certificate profile, you must select a previously created Trusted CA certificate profile.|
To use SCEP certificate profiles, you must integrate the following on-premises infrastructure with  [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]:

-   A server that runs the Network Device Enrollment Service

-   An Enterprise Certification Authority

-   The Intune Certificate Connector, which installs on the Windows Server 2012 R2 server that runs NDES

To use .PFX Certificate profiles, you must integrate the following on-premises infrastructure with  [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]:

-   An enterprise certification authority.

-   A computer that can communicate with the Certification Authority, or use the Certification Authority computer itself.

    The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.

In this topic:

-   [Requirements for certificate profiles](../Topic/Enable_access_to_company_resources_using_certificate_profiles_with_Microsoft_Intune.md#BKMK_CertProfileRequirements)

-   [Configure your infrastructure](../Topic/Enable_access_to_company_resources_using_certificate_profiles_with_Microsoft_Intune.md#BKMK_ConfigureInfrastructure)

-   [Configure certificate profiles](../Topic/Enable_access_to_company_resources_using_certificate_profiles_with_Microsoft_Intune.md#BKMK_ConfigProfiles)

-   [Deploy certificate profiles](../Topic/Enable_access_to_company_resources_using_certificate_profiles_with_Microsoft_Intune.md#BKMK_Deploy)

## <a name="BKMK_CertProfileRequirements"></a>Requirements for certificate profiles

### <a name="BKMK_OnPremises"></a>On-premises Infrastructure

|Infrastructure|Details|
|------------------|-----------|
|**Active Directory domain**|All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.|
|**Certification Authority server**|Referred to as the issuing CA, you must have an Enterprise Certification Authority (CA) that runs on an Enterprise edition of [!INCLUDE[nextref_server_7](../Token/nextref_server_7_md.md)] or later. A Standalone CA is not supported.<br /><br />For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).<br /><br />If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).|
|For SCEP profile only:<br />                    **NDES Server**|On a server that runs [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] or later, you must setup up the Network Device Enrollment Service:<br /><br />[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not support using the Network Device Enrollment Service when it runs on a server that also runs the Enterprise CA.<br /><br />See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] to host the Network Device Enrollment Service.|
|For .PFX Certificate profile only: **Computer that can communicate with Certification Authority**|Alternatively, use the Certification Authority computer itself.|
|**Web Application Proxy Server** (optional)|You can use a server that runs [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] or later as a Web Application Proxy (WAP) server. This configuration:<br /><br />Allows devices to receive certificates using an Internet connection.<br /><br />Is a security recommendation when devices connect through the Internet to receive and renew certificates.<br /><br />The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service. This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).<br /><br />Also, the server that hosts WAP must have a SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.<br /><br />These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.<br /><br />For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx). For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|
|**Microsoft Intune Certificate Connector**|You use the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**). Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector. For .PFX Certificate profiles, install the Certificate Connector on the computer that communicates with the Certification Authority.|

### <a name="BKMK_CertsAndTemplates"></a>Certificates and Templates

|Object|Details|
|----------|-----------|
|**Certificate Template**|You configure this template on your issuing CA.|
|**Client authentication certificate**|Requested from your issuing CA or public CA, you install this certificate on the NDES Server.|
|**Server authentication certificate**|Requested from your issuing CA or public CA, you install and bind this SSL certificate in IIS on the NDES server.|
|**Trusted Root CA certificate**|You export this as a **.cer** file from the issuing CA or any device which trusts the issuing CA, and deploy it to devices by using the Trusted CA certificate profile.<br /><br />You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.<br /><br />You can use additional Trusted Root CA certificates when needed. For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.|

### <a name="BKMK_Accounts"></a>Accounts

|Name|Details|
|--------|-----------|
|**NDES service account**|You specify a domain user account to use as the NDES Service account.|

## <a name="BKMK_ConfigureInfrastructure"></a>Configure your infrastructure
Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):

**Task 1** - Configure certificate templates on the certification authority 
**Task 2**, for SCEP profile only:
                     - Configure prerequisites on the NDES server 
**Task 3**, for SCEP profile only:
                     - Configure NDES for use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]
**Task 4** - Enable, install, and configure the Intune Certificate Connector

### <a name="BKMK_ConfigOnPremTask1"></a>Task 1 - Configure certificate templates on the certification authority
In this task you will:

-   Create a NDES service account

    > [!NOTE]
    > To revoke certificates the NDES service account requires *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.

-   Configure a certificate template for NDES

-   Publish the certificate template for NDES

##### To configure the certification authority

1.  Create a domain user account to use as the NDES service account. You will specify this account when you configure templates on the issuing CA before you install and configure NDES.

2.  On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.

    The template must have the following configurations:

    -   Specify a friendly **Template display name** for the template.

    -   On the **Subject Name** tab, select **Supply in the request**. (Security is enforced by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy module for NDES).

    -   On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.

        > [!IMPORTANT]
        > For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.

    -   On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template.

3.  Review the **Validity period** on the **General** tab of the template. By default, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] uses the value configured in the template. However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Administrator console. If you want to always use the value in the template, skip the remainder of this step.

    > [!IMPORTANT]
    > The iOS and Mac OS X platforms always uses the value set in the template regardless of other configurations you make.

    To configure the CA to allow the requester to specify the validity period, on the CA run the following commands:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  On the issuing CA, use the Certification Authority snap-in to publish the certificate template.

    1.  Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.

    2.  Validate that the template published by viewing it under the **Certificate Templates** folder.

5.  For .PFX profiles: on the CA computer ensure that the computer that hosts the Intune Certificate Connector has enroll permission, so that it can access the template used in creating the .PFX profile. Set that permission on the **Security** tab of the CA computer properties.

### <a name="BKMK_ConfigOnPremTask2"></a>Task 2 (SCEP profile only) - Configure prerequisites on the NDES server
In this task you will:

-   Add NDES to a Windows Server and configure IIS to support NDES

-   Add the NDES Service account to the IIS_IUSR group

-   Set the SPN for the NDES Service account

##### To configure prerequisites for the NDES Server

1.  On the server that will hosts NDES, you must log on as a an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:

    1.  In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services. Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.

        > [!TIP]
        > On the **Installation progress** page of the wizard, do not click **Close**. Instead, click the link for **Configure Active Directory Certificate Services on the destination server**. This opens the **AD CS Configuration** wizard that you use for the next task. After AD CS Configuration opens, you can close the Add Roles and Features wizard.

    2.  When NDES is added to the server, the wizard also installs IIS. Ensure IIS has the following configurations:

        -   **Web Server** &gt; **Security** &gt; **Request Filtering**

        -   **Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**. Installing ASP.NET 3.5 will install .NET Framework 3.5. When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.

        -   **Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**. Installing ASP.NET 4.5 will install .NET Framework 4.5. When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.

        -   **Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**

        -   **Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**

2.  On the server, add the NDES service account as a member of the **IIS_IUSR** group.

3.  Run the following command to set the SPN of the NDES Service account:

    -   **setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**

    For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:

    -   **setspn –s http/Server01.contoso.com contoso\NDESService**

### <a name="BKMK_ConfigOnPremTask3"></a>Task 3 (SCEP profile only) - Configure NDES for use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]
In this task you will:

-   Configure NDES for use with the issuing CA

-   Bind the server authentication (SSL) certificate in IIS

-   Configure Request Filtering in IIS

##### To configure NDES for use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

1.  On the NDES Server, open the AD CS Configuration wizard and then make the following configurations.

    > [!TIP]
    > If you clicked the link in the previous task, this wizard is already open. Otherwise, open Server Manager to access the post-deployment configuration for Active Directory Certificate Services.

    -   On the **Role Services** Page, select the **Network Device Enrollment Service**.

    -   On the **Service Account for NDES** page, specify the NDES Service Account.

    -   On the **CA for NDES** page, click **Select**, and then select the issuing CA where you configured the certificate template.

    -   On the **Cryptography for NDES** page, set the key length to meet your company requirements.

    On the **Confirmation** page, click **Configure** to complete the wizard.

2.  After the wizard completes, edit the following registry key on the NDES Server:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    To edit this key, identify the certificate template's **Purpose**, as found on its **Request Handling** tab, and then edit the corresponding entry in the registry by replacing the existing data with the name of the certificate template (not the display name of the template) that you specified in Task 1. The following table maps the certificate template purpose to the values in the registry:

    |Certificate template Purpose (On the Request Handling tab)|Registry value to edit|Value seen in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console for the SCEP profile|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Signature|SignatureTemplate|Digital Signature|
    |Encryption|EncryptionTemplate|Key Encipherment|
    |Signature and encryption|GeneralPurposeTemplate|Key Encipherment<br /><br />Digital Signature|
    For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.

3.  After editing the registry, run **iisreset** on the server to force the server to pick up recent configuration changes.

##### To Install and bind certificates on the NDES Server

1.  On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA. You will then bind this SSL certificate in IIS.

    > [!TIP]
    > After you bind the SSL certificate in IIS, you will also install a client authentication certificate. This certificate can be issued by any CA that is trusted by the NDES Server. Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKU’s). Review the following steps for information about these authentication certificates.

    1.  After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.

    2.  Click **Add**, set **Type** to **https**, and then ensure the port is **443**. (Only port 443 is supported for standalone [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]).

    3.  For **SSL certificate**, specify the server authentication certificate.

        > [!NOTE]
        > If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.

2.  On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority. This can be the same certificate as the server authentication certificate if that certificate has both capabilities.

    The client authentication certificate must have the following properties:

    **Enhanced Key Usage** - This must include **Client Authentication**.

    **Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).

##### To configure IIS Request Filtering

1.  On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.

2.  Click **Edit Feature Settings**, and then set the following:

    **query string (Bytes)** = **65534**

    **Maximum URL length (Bytes)** = **65534**

3.  Review the following registry key:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Ensure the following values are set as DWORD entries:

    Name: **MaxFieldLength**, with a decimal value of **65534**

    Name: **MaxRequestBytes**, with a decimal value of **65534**

4.  Reboot the NDES server. The server is now ready to support the Certificate Connector.

### <a name="BKMK_ConfigOnPremTask4"></a>Task 4 - Enable, install, and configure the Intune Certificate Connector  - For SCEP and .PFX certificates.
In this task you will:

Enable support for NDES in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

Download, install, and configure the Certificate Connector on the NDES Server

##### To enable support for the Certificate Connector

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Certificate Connector**.

2.  Click **Configure On-Premises Certificate Connector**.

3.  Select **Enable Certificate Connector**, and then click **OK**.

##### To download, install and configure the Certificate Connector

1.  Open the [Intune administration console](https://manage.microsoft.com), and then click **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.

2.  After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**):

    -   For .PFX certificates, run the installer on the computer that is able to connect with the Certification Authority. Choose the .PFX Distribution option then click Install. When the installation has completed, continue by creating a certificate profile as described in [Configure certificate profiles](../Topic/Enable_access_to_company_resources_using_certificate_profiles_with_Microsoft_Intune.md#BKMK_ConfigProfiles).

    -   For SCEP certificates, run the installer on a Windows Server 2012 R2 server

    For the SCEP option, the installer also installs the policy module for NDES and the CRP Web Service. (The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)

    > [!NOTE]
    > When you install NDES for standalone [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], the CRP service automatically installs with the Certificate Connector. When you use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] with Configuration Manager, you install the Certificate Registration Point as a separate site system role.

3.  When prompted for the client certificate for the Certificate Connector, click **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.

    After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface. Although the certificate you selected is not shown, click **Next** to view the properties of that certificate. Then click **Next**, and then click **Install**.

4.  After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.

    > [!TIP]
    > If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:
    > 
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In the **Certificate Connector** UI:

    Click **Sign In** and enter your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service administrator credentials, or credentials for a tenant administrator with the global administration permission.

    If your organization uses a proxy server and the proxy is required for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.

    Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.

    You can now close the Certificate Connector UI.

6.  Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Certificate Connector Service**, and then click **Restart**.

To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

You are now ready to configure certificate profiles.

## <a name="BKMK_ConfigProfiles"></a>Configure certificate profiles
After your infrastructure and certificates are configured, you can configure certificate profiles:

**Task 1** - Export the Trusted Root CA certificate 
**Task 2** - Create Trusted CA certificate profiles 
**Task 3** - Either:

Create SCEP certificate profiles

Create .PFX certificate profiles

### <a name="BKMK_ConfigExportRootCA"></a>Task 1 - Export the Trusted Root CA certificate
Export the Trusted Root CA certificate as a **.cer** file from the issuing CA, or any device that trusts your issuing CA. You do not export the private key.

You will import this certificate when you configure a Trusted CA certificate profile.

### <a name="BKMK_ConfigRootCA"></a>Task 2 - Create Trusted CA certificate profiles
You must create a **Trusted CA certificate profile** before you can create a **Simple Certificate Enrollment Protocol settings profile**. Both profiles are required for each mobile device platform.

##### To create a trusted certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), and click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; Trusted Certificate Profile (Android 4 and later)**

    **iOS &gt; Trusted Certificate Profile (iOS 5 and later)**

    **iOS &gt; Trusted Certificate Profile (iOS 5 and later)**

    **Mac OS X &gt; Trusted Certificate Profile (Mac OS X 10.9 and later)**

    **Windows Phone and Enrolled Windows Devices &gt; Trusted Certificate Profile (Windows 8.1 and later)**

    **Windows Phone and Enrolled Windows Devices &gt; Trusted Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

3.  Use the following information to configure the trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1:

    |Setting name|Platform|More information|
    |----------------|------------|--------------------|
    |**Name**|All|Provide a descriptive name for the certificate profile.|
    |**Description**|All|Provide an optional description for the certificate.|
    |**Certificate file**|All|Click **Import**, and then select the Trusted Root CA certificate (**.cer**) that you exported from your issuing CA.|
    |**Destination store**|Windows 8.1|For devices that have more than one certificate store, select where to store the certificate. Select from:<br /><br />**Computer certificate store – Root**<br /><br />**Computer Certificate store – Intermediate**<br /><br />**User certificate store – Intermediate**<br /><br />For devices that have only one store, this setting is ignored.|

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

### <a name="BKMK_ConfigSCEP"></a>Task 3 – Create SCEP or .PFX certificate profiles
After you have created a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use. When you create a SCEP certificate profile, you must specify a Trusted CA certificate profile for that same platform. This links the two certificate profiles, although, you must still deploy each profile separately.

##### To create a SCEP certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; SCEP Certificate Profile (Android 4 and later)**

    **iOS &gt; SCEP Certificate Profile (iOS 5 and later)**

    **Mac OS X &gt; SCEP Certificate Profile (Mac OS X 10.9 and later)**

    **Windows Phone and Enrolled Windows Devices &gt; SCEP Certificate Profile (Windows 8.1 and later)**

    **Windows Phone and Enrolled Windows Devices &gt; SCEP Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

3.  Use the following information to configure the SCEP certificate profile settings for Android, iOS, Mac OS X, Windows 8.1 and later, and Windows Phone 8.1 and later:

    |Setting name|Platform|More information|
    |----------------|------------|--------------------|
    |**Name**|All|Provide a descriptive name for the certificate profile.|
    |**Description**|All|Provide an optional description for the certificate.|
    |**Renewal threshold (%)**|All|Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.|
    |**Key Storage Provider (KSP)**|Android <br />Windows 8.1 <br />Windows Phone 8.1|Specify where the key to the certificate will be stored. Choose from one of the following:<br /><br />**Enroll to Trusted Platform Module (TPM) if present, otherwise enroll to software KSP** - Enrolls the key to the TPM. If the TPM is not present, the key will be installed to the storage provider for the software key.<br /><br />**Enroll to Trusted Platform Module (TPM), otherwise fail** - Enrolls the key to the TPM. If the TPM module is not present, the installation will fail<br /><br />**Enroll  to Passport for Work KSP, otherwise fail (Windows 10 and later)** - Enrolls the key to Passport for Work, described in [Control Microsoft Passport settings on devices with Microsoft Intune](../Topic/Control_Microsoft_Passport_settings_on_devices_with_Microsoft_Intune.md). This option also enables you to **Require multi-factor authentication** during enrollment of devices before issuing certificates to those devices. See [Protect Windows devices with multi-factor authentication](../Topic/Protect_Windows_devices_with_multi-factor_authentication.md) for more information.<br /><br />**Enroll to Software KSP** - Enrolls the key to the storage provider for the software key.|
    |**SCEP server URL**|All|Enter a URL (with the **http://** or **https://** prefix), then click **Add**; or select a URL, and then click **Delete**.<br /><br />For example, a SCEP server URL might resemble the following:: **https://mdmndes1.contoso.com/certsrv/mscep/mscep.dll**<br /><br />Each SCEP profile supports a single SCEP server URL.|
    |**Subject name format**|Android <br />Windows 8.1 <br />Windows Phone 8.1|From the list, select how [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] automatically creates the subject name in the certificate request. If the certificate is for a user, you can also include the user's email address in the subject name.<br /><br />You can select **Common Name** or **Common Name and email address**.|
    |**Subject Alternative Name**|All|Select **Email Address**, **User principal name (UPN)**, or both.|
    |**Certificate validity period**|All|Specify the amount of time before the certificate expires.|
    |**Key Usage**|All|Specify key usage options for the certificate. You can choose from the following options:<br /><br />**Digital Signature** (SignatureTemplate) – Use to digitally sign data.<br /><br />**Key Encipherment** (EncryptionTemplate) - Use for encryption.<br /><br />**Key Encipherment + Digital Signature** (GeneralPurposeTemplate) – Use to digitally sign and encrypt data.|
    |**Key size (bits)**|All|Select the size of the key in bits that is supported by your device.<br /><br />Select **1024** or **2048**.|
    |**Hash algorithm**|Android <br />Windows 8.1 <br />Windows Phone 8.1|Select one of the available hash algorithm types to use with this certificate. Select the strongest level of security that the connecting devices support.<br /><br />Select **SHA-2**.|
    |**Extended Key Usage**|All|Click **Select** to add values for the certificate’s intended purpose. In most cases, the certificate will require **Client Authentication** so that the user or device can authenticate to a server. However, you can add any other key usages as required.|
    |**Select Root Certificate**|All|Click **Select** to choose a root CA certificate profile that you have previously configured and deployed to the user or device. This CA certificate must be the root certificate for the CA that will issue the certificate that you are configuring in this certificate profile.|

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

##### To create a .PFX certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    -   **Android &gt;.PFX Certificate Profile (Android 4 and later)**

    -   **Windows Phone and Enrolled Windows Devices &gt; .PFX Certificate Profile (Windows 10 and later)**

    -   **Windows Phone and Enrolled Windows Devices &gt; .PFX Certificate Profile (Windows Phone 10 and later)**

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

3.  Use the following information to configure the .PFX  certificate profile settings for Android, Windows 10, and Windows Phone 10:

    |Setting name|Platform|More information|
    |----------------|------------|--------------------|
    |**Name**|Android <br />Windows 10<br />Windows Phone 10|Provide a descriptive name for the certificate profile.|
    |**Description**|Android <br />Windows 10<br />Windows Phone 10|Provide an optional description for the certificate.|
    |**Renewal threshold (%)**|Android <br />Windows 10<br />Windows Phone 10|Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.|
    |**Certification authority**|Android <br />Windows 10<br />Windows Phone 10|Provide the FQDN of the certification authority, for example, *device.certs.contoso.com*.|
    |**Certification authority name**|Android <br />Windows 10<br />Windows Phone 10|Provide the name of the certification authority, such as *device-contoso-CA*.|
    |**Certification template name**|Android <br />Windows 10<br />Windows Phone 10|Provide the name of the certification template (not the display name).|
    |**Subject name format**|Android <br />Windows 10<br />Windows Phone 10|Provide a common name or a common name and email address|
    |**Subject alternative name**|Android <br />Windows 10<br />Windows Phone 10|Choose the subject alternative names.|
    |**Certificate validity period**|Android <br />Windows 10<br />Windows Phone 10|Specify the amount of time before the certificate expires.|

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

## <a name="BKMK_Deploy"></a>Deploy certificate profiles
When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on devices, and the SCEP or .PFX certificate profile is used by the device to create a certificate request by the device.

Certificate profiles install only on applicable devices based on the platform you use when creating the profile.

-   You can deploy certificate profiles to user collections or device collections.

    > [!TIP]
    > To allow certificates to be published to devices quickly after the device enrolls, deploy the certificate profile to a user group (not a device group). If you deploy to a device group, a full device registration must take place before the device receives policy.

-   Although each profile is deployed separately, both the Trusted Root and the SCEP/.PFX profile must be deployed or else the SCEP/.PFX certificate policy will fail.

You deploy certificate profiles the same way you deploy other policy for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For information about how to deploy and manage policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).



