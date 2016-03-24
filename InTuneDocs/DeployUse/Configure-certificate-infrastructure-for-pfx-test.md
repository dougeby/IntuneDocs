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

To use .PFX Certificate profiles, in addition to the Enterprise Certification Authority, you  also need:

-   A computer that can communicate with the Certification Authority, or use the Certification Authority computer itself.

 -  The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.

### <a name="BKMK_OnPremises"></a>On-premises infrastructure


-    **Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.

-  **Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of [!INCLUDE[nextref_server_7](../Token/nextref_server_7_md.md)] or later. A Standalone CA is not supported. For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).
    If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).

 -  **Computer that can communicate with Certification Authority**: Alternatively, use the Certification Authority computer itself.
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
|**Trusted Root CA certificate**|You export this as a **.cer** file from the issuing CA or any device which trusts the issuing CA, and deploy it to devices by using the Trusted CA certificate profile.<br /><br />You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.<br /><br />You can use additional Trusted Root CA certificates when needed. For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.|


## <a name="BKMK_ConfigureInfrastructure"></a>Configure your infrastructure
Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):

**Task 1** - Configure certificate templates on the certification authority
**Task 2** - Enable, install, and configure the Intune Certificate Connector

### <a name="BKMK_ConfigOnPremTask1"></a>Task 1 - Configure certificate templates on the certification authority
In this task you will publish the certificate template

##### To configure the certification authority

1.  On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with .pFX.

    The template must have the following configurations:

    -   Specify a friendly **Template display name** for the template.

    -   On the **Subject Name** tab, select **Supply in the request**. (Security is enforced by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy module for NDES).

    -   On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.

        > [!IMPORTANT]
        > For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.


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

5.  On the CA computer ensure that the computer that hosts the Intune Certificate Connector has enroll permission, so that it can access the template used in creating the .PFX profile. Set that permission on the **Security** tab of the CA computer properties.

### <a name="BKMK_ConfigOnPremTask4"></a>Task 4 - Enable, install, and configure the Intune Certificate Connector
In this task you will:

Download, install, and configure the Certificate Connector

##### To enable support for the Certificate Connector

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Certificate Connector**.

2.  Click **Configure On-Premises Certificate Connector**.

3.  Select **Enable Certificate Connector**, and then click **OK**.

##### To download, install and configure the Certificate Connector

1.  Open the [Intune administration console](https://manage.microsoft.com), and then click **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.

2.  After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**):

  Run the installer on the computer that is able to connect with the Certification Authority. Choose the .PFX Distribution option then click Install. When the installation has completed, continue by creating a certificate profile as described in [Configure certificate profiles](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md#BKMK_ConfigProfiles).

   <!-- Not sure about step 3 below -->

3.  When prompted for the client certificate for the Certificate Connector, click **Select**, and select the **client authentication** certificate you installed in Task 3.

    After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface. Although the certificate you selected is not shown, click **Next** to view the properties of that certificate. Then click **Next**, and then click **Install**.

4.  After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.

    > [!TIP]
    > If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In the **Certificate Connector** UI:

    Click **Sign In** and enter your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service administrator credentials, or credentials for a tenant administrator with the global administration permission.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.

    You can now close the Certificate Connector UI.

6.  Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Certificate Connector Service**, and then click **Restart**.

To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## Next steps
You are now ready to configure certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).
