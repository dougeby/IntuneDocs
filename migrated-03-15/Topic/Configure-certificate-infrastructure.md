---
title: Configure certificate infrastructure
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b
author: Lizap
---
# Configure certificate infrastructure
This topic describes what you need in order to create and deploy certificate profiles.

To do any certificate-based authentication in your organization, you need an Enterprise Certification Authority.

To use SCEP certificate profiles, in addition to the Enterprise Certification Authority, you  also need:

-   A server that runs the Network Device Enrollment Service

-   The Intune Certificate Connector, which installs on the Windows Server 2012 R2 server that runs NDES

To use .PFX Certificate profiles, in addition to the Enterprise Certification Authority, you  also need:

-   A computer that can communicate with the Certification Authority, or use the Certification Authority computer itself.

 -   The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.

### <a name="BKMK_OnPremises"></a>On-premises infrastructure


-    **Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.

-  **Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of [!INCLUDE[nextref_server_7](../Token/nextref_server_7_md.md)] or later. A Standalone CA is not supported. For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).
    If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).
 
 -  **NDES Server** (SCEP only): On a server that runs [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] or later, you must setup up the Network Device Enrollment Service (NDES). [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not support using NDES when it runs on a server that also runs the Enterprise CA. See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] to host the Network Device Enrollment Service.|
-  **Computer that can communicate with Certification Authority** (.PFX only):Alternatively, use the Certification Authority computer itself.
-  **Microsoft Intune Certificate Connector**: You use the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**). Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector. For .PFX Certificate profiles, install the Certificate Connector on the computer that communicates with the Certification Authority.
-  **Web Application Proxy Server** (optional): You can use a server that runs [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] or later as a Web Application Proxy (WAP) server. This configuration:
    -  Allows devices to receive certificates using an Internet connection.
    -  Is a security recommendation when devices connect through the Internet to receive and renew certificates.
    
 > [!NOTE]           
> -    The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service. This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Also, the server that hosts WAP must have a SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server. These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.
    For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx). For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|


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
    > To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.

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

    -   For .PFX certificates, run the installer on the computer that is able to connect with the Certification Authority. Choose the .PFX Distribution option then click Install. When the installation has completed, continue by creating a certificate profile as described in [Configure certificate profiles](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md#BKMK_ConfigProfiles).

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

    If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.

    Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.

    You can now close the Certificate Connector UI.

6.  Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Certificate Connector Service**, and then click **Restart**.

To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## Next steps
You are now ready to configure certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).
  
