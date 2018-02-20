---
title: Configure and manage SCEP certificates with Intune
titlesuffix: "Azure portal"
description: Learn how to configure your infrastructure, then create and assign Intune SCEP certificate profiles."
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---
# Configure and manage SCEP certificates with Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic shows how to configure your infrastructure, then create and assign Simple Certificate Enrollment Protocol (SCEP) certificate profiles with Intune.

## Configure on-premises infrastructure

-    **Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.

-  **Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later. A Standalone CA is not supported. For details, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).
    If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).

-  **NDES Server**: On a server that runs Windows Server 2012 R2 or later, you must set up the Network Device Enrollment Service (NDES). Intune does not support using NDES when it runs on a server that also runs the Enterprise CA. See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure Windows Server 2012 R2 to host the Network Device Enrollment Service.
The NDES server must be domain joined to the domain that hosts the CA, and not be on the same server as the CA. More information about deploying the NDES server in a separate forest, isolated network, or internal domain can be found in [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune Certificate Connector**: Use the Azure portal to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**). Then you can run **ndesconnectorssetup.exe** on the server hosting the Network Device Enrollment Service (NDES) role where you want to install the Certificate Connector. 
-  **Web Application Proxy Server** (optional): Use a server that runs Windows Server 2012 R2  or later as a Web Application Proxy (WAP) server. This configuration:
    -  Allows devices to receive certificates using an Internet connection.
    -  Is a security recommendation when devices connect through the Internet to receive and renew certificates.

 > [!NOTE]           
> -    The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service. This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Also, the server that hosts WAP must have an SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server. These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.
    For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx). For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|

### Network requirements

From the Internet to perimeter network, allow port 443 from all hosts/IP addresses on the internet to the NDES server.

From the perimeter network to trusted network, allow all ports and protocols needed for domain access on the domain-joined NDES server. The NDES server needs access to the certificate servers, DNS servers, Configuration Manager servers, and domain controllers.

We recommend publishing the NDES server through a proxy, such as the [Azure AD application proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx), or a third-party proxy.


### Certificates and templates

|Object|Details|
|----------|-----------|
|**Certificate Template**|Configure this template on your issuing CA.|
|**Client authentication certificate**|Requested from your issuing CA or public CA; you install this certificate on the NDES Server.|
|**Server authentication certificate**|Requested from your issuing CA or public CA; you install and bind this SSL certificate in IIS on the NDES server.|
|**Trusted Root CA certificate**|You export this certificate as a **.cer** file from the root CA or any device that trusts the root CA, and assign it to devices by using the Trusted CA certificate profile.<br /><br />You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.<br /><br />You can use additional Trusted Root CA certificates when needed. For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.|

### Accounts

|Name|Details|
|--------|-----------|
|**NDES service account**|Specify a domain user account to use as the NDES Service account.|

## Configure your infrastructure
Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):

**Step 1**: Create an NDES service account

**Step 2**: Configure certificate templates on the certification authority

**Step 3**: Configure prerequisites on the NDES server

**Step 4**: Configure NDES for use with Intune

**Step 5**: Enable, install, and configure the Intune Certificate Connector

#### Step 1 - Create an NDES service account

Create a domain user account to use as the NDES service account. You specify this account when you configure templates on the issuing CA before you install and configure NDES. Make sure the user has the default rights, **Logon Locally**, **Logon as a Service** and **Logon as a batch job** rights. Some organizations have hardening policies that disable those rights.

#### Step 2 - Configure certificate templates on the certification authority
In this task, you will:

-   Configure a certificate template for NDES

-   Publish the certificate template for NDES

##### To configure the certification authority

1.  Log on as an enterprise administrator.

2.  On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.

	>[!NOTE]
	> The NDES certificate template must be based off a v2 Certificate Template (with Windows 2003 compatibility).

    The template must have the following configurations:

    -   Specify a friendly **Template display name** for the template.

    -   On the **Subject Name** tab, select **Supply in the request**. (Security is enforced by the Intune policy module for NDES).

    -   On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.

        > [!IMPORTANT]
        > For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.

    -   On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template. Intune admins who create SCEP profiles require **Read** rights so that they can browse to the template when creating SCEP profiles.

    > [!NOTE]
    > To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.

3.  Review the **Validity period** on the **General** tab of the template. By default, Intune uses the value configured in the template. However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console. If you want to always use the value in the template, skip the remainder of this step.

    > [!IMPORTANT]
    > iOS and macOS always use the value set in the template regardless of other configurations you make.

Here are screenshots of an example template configuration.

![Template, request handling tab](.\media\scep_ndes_request_handling.png)

![Template, subject name tab](.\media\scep_ndes_subject_name.jpg)

![Template, security tab](.\media\scep_ndes_security.jpg)

![Template, extensions tab](.\media\scep_ndes_extensions.jpg)

![Template, issuance requirements tab](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > For Application Policies, only add the application policies required. Confirm your choices with your security admins.



To configure the CA to allow the requester to specify the validity period:

1. On the CA run the following commands:
	- **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
	- **net stop certsvc**
	- **net start certsvc**
2. On the issuing CA, use the Certification Authority snap-in to publish the certificate template.
	Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.
3. Validate that the template published by viewing it under the **Certificate Templates** folder.


#### Step 3 - Configure prerequisites on the NDES server
In this task you:

-   Add NDES to a Windows Server and configure IIS to support NDES

-   Add the NDES Service account to the IIS_IUSR group

-   Set the SPN for the NDES Service account




   1.  On the server that hosts NDES, log on as an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:

    1.  In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services. Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.

        > [!TIP]
        > On the **Installation progress** page of the wizard, do not click **Close**. Instead, click the link for **Configure Active Directory Certificate Services on the destination server**. This opens the **AD CS Configuration** wizard that you use for the next task. After AD CS Configuration opens, you can close the Add Roles and Features wizard.

    2.  When NDES is added to the server, the wizard also installs IIS. Ensure IIS has the following configurations:

        -   **Web Server** &gt; **Security** &gt; **Request Filtering**

        -   **Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**. Installing ASP.NET 3.5 installs .NET Framework 3.5. When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.

        -   **Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**. Installing ASP.NET 4.5 installs .NET Framework 4.5. When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.

        -   **Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**

        -   **Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**

  2.  On the server, add the NDES service account as a member of the **IIS_IUSR** group.

   3.  In an elevated command prompt, run the following command to set the SPN of the NDES Service account:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### Step 4 - Configure NDES for use with Intune
In this task, you will:

-   Configure NDES for use with the issuing CA

-   Bind the server authentication (SSL) certificate in IIS

-   Configure Request Filtering in IIS


1.  On the NDES Server, open the AD CS Configuration wizard and then make the following configurations:

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

    |Certificate template Purpose (On the Request Handling tab)|Registry value to edit|Value seen in the Intune admin console for the SCEP profile|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Signature|SignatureTemplate|Digital Signature|
    |Encryption|EncryptionTemplate|Key Encipherment|
    |Signature and encryption|GeneralPurposeTemplate|Key Encipherment<br /><br />Digital Signature|
    For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.

3. The NDES server receives long URLs (queries), which require that you add two registry entries:

    |Location|Value|Type|Data|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (decimal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (decimal)|


4. In IIS manager, select **Default Web Site** -> **Request Filtering** -> **Edit Feature Setting**, and change the **Maximum URL length** and **Maximum query string** to *65534*, as shown.

    ![IIS max URL and query length](.\media\SCEP_IIS_max_URL.png)

5.  Restart the server. Running **iisreset** on the server is not sufficient to finalize these changes.
6. Browse to http://*FQDN*/certsrv/mscep/mscep.dll. You should see an NDES page similar to this:

    ![Test NDES](.\media\SCEP_NDES_URL.png)

    If you get a **503 Service unavailable**, check the event viewer. It's likely that the application pool is stopped due to a missing right for the NDES user. Those rights are described in Task 1.

##### To Install and bind certificates on the NDES Server

1.  On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA. You then bind this SSL certificate in IIS.

    > [!TIP]
    > After you bind the SSL certificate in IIS, install a client authentication certificate. This certificate can be issued by any CA that is trusted by the NDES Server. Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKUs). Review the following steps for information about these authentication certificates.

    1.  After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.

    2.  Click **Add**, set **Type** to **https**, and then ensure the port is **443**. (Only port 443 is supported for standalone Intune.

    3.  For **SSL certificate**, specify the server authentication certificate.

        > [!NOTE]
        > If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.

2.  On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority. This can be the same certificate as the server authentication certificate if that certificate has both capabilities.

    The client authentication certificate must have the following properties:

    **Enhanced Key Usage** - This must include **Client Authentication**.

    **Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).

##### To configure IIS request filtering

1.  On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.

2.  Click **Edit Feature Settings**, and then set the  values:

    **query string (Bytes)** = **65534**

    **Maximum URL length (Bytes)** = **65534**

3.  Review the following registry key:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Ensure the following values are set as DWORD entries:

    Name: **MaxFieldLength**, with a decimal value of **65534**

    Name: **MaxRequestBytes**, with a decimal value of **65534**

4. Reboot the NDES server. The server is now ready to support the Certificate Connector.

#### Step 5 - Enable, install, and configure the Intune certificate connector
In this task, you will:

- Enable support for NDES in Intune.
- Download, install, and configure the Certificate Connector on the server hosting the Network Device Enrollment Service (NDES) role a server in your environment. To increase scalability of the NDES implementation in your organization, you can install multiple NDES servers with a Microsoft Intune Certificate Connector on each NDES server.

##### To download, install, and configure the certificate connector
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **More Services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, select **Device configuration**.
4. On the **Device configuration** pane, select **Certification Authority**.
5. Click **Add** and select **Download the connector file**. Save the download to a location where you can access it from the server where you are going to install it. 
6.  After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**) on the server hosting the Network Device Enrollment Service (NDES) role. The installer also installs the policy module for NDES and the CRP Web Service. (The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)

    > [!NOTE]
    > When you install NDES for standalone Intune, the CRP service automatically installs with the Certificate Connector. When you use Intune with Configuration Manager, you install the Certificate Registration Point as a separate site system role.

3.  When prompted for the client certificate for the Certificate Connector, choose **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.

    After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface. Although the certificate you selected is not shown, click **Next** to view the properties of that certificate. Then click **Next**, and then click **Install**.

4.  After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.

    > [!TIP]
    > If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In the **Certificate Connector** UI:

    Click **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.

    > [!IMPORTANT]
    > The user account must be assigned a valid Intune license. If the user account does not have a valid Intune license, then NDESConnectorUI.exe fails.

    If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.

    Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.

    You can now close the Certificate Connector UI.

6.  Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Intune Connector Service**, and then click **Restart**.

To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## How to create a SCEP certificate profile

1. In the Azure portal, select the **Device configuration** workload.
2. On the **Device configuration** pane, select **Manage** > **Profiles**.
3. On the profiles pane, select **Create profile**.
4. On the **Create profile** pane, enter a **Name** and **Description** for the SCEP certificate profile.
5. From the **Platform** drop-down list, select the device platform for this SCEP certificate. Currently, you can select one of the following platforms for device restriction settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, select **SCEP certificate**.
7. On the **SCEP Certificate** pane, configure the following settings:
	- **Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.<br>You can specify a value that is lower than the validity period in the specified certificate template, but not higher. For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years. The value must also be lower than the remaining validity period of the issuing CA's certificate. 
	- **Key storage provider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Specify where the key to the certificate is stored. Choose from one of the following values:
		- **Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**
		- **Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**
		- **Enroll to Passport, otherwise fail (Windows 10 and later)**
		- **Enroll to Software KSP**
	- **Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request. If the certificate is for a user, you can also include the user's email address in the subject name. Choose from:
		- **Not configured**
		- **Common name**
		- **Common name including email**
		- **Common name as email**
		- **IMEI (International Mobile Equipment Identity)**
		- **Serial number**
		- **Custom** - When you select this option, another drop-down field is displayed. You use this field to enter a custom subject name format. The two variables supported for the custom format are **Common Name (CN)** and **Email (E)**. By using a combination of one or many of these variables and static strings, you can create a custom subject name format, like this one: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** In this example, you created a subject name format that, in addition to the CN and E variables, uses strings for Organizational Unit, Organization, Location, State, and Country values. [This topic](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) shows the **CertStrToName** function and its supported strings.
		
	- **Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request. For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name. If the client certificate is used to authenticate to a Network Policy Server, you must set the subject alternative name to the UPN. 
	- **Key usage** - Specify key usage options for the certificate. You can choose from the following options: 
		- **Key encipherment:** Allow key exchange only when the key is encrypted. 
		- **Digital signature:** Allow key exchange only when a digital signature helps protect the key. 
	- **Key size (bits)** - Select the number of bits that is contained in the key. 
	- **Hash algorithm** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Select one of the available hash algorithm types to use with this certificate. Select the strongest level of security that the connecting devices support. 
	- **Root Certificate** - Choose a root CA certificate profile that you have previously configured and assigned to the user or device. This CA certificate must be the root certificate for the CA that issues the certificate that you are configuring in this certificate profile. 
	- **Extended key usage** - Select **Add** to add values for the certificate's intended purpose. In most cases, the certificate requires **Client Authentication** so that the user or device can authenticate to a server. However, you can add any other key usages as required. 
	- **Enrollment Settings**
		- **Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.
		- **SCEP Server URLs** - Specify one or more URLs for the NDES Servers that issues certificates via SCEP. 
8. Select **OK**, and then go back to the **Create profile** pane, and select **Create**.

The profile is created and appears on the profiles list pane.

## How to assign the certificate profile

Consider the following before you assign certificate profiles to groups:

- When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device. The device uses the SCEP certificate profile to create a certificate request by the device.
- Certificate profiles install only on devices running the platform you use when you created the profile.
- You can assign certificate profiles to user collections or to device collections.
- To publish a certificate to a device quickly after the device enrolls, assign the certificate profile to a user group rather than to a device group. If you assign to a device group, a full device registration is required before the device receives policies.
- Although you assign each profile separately, you also need to assign the Trusted Root CA and the SCEP or PKCS profile. Otherwise, the SCEP or PKCS certificate policy fails.

For information about how to assign profiles, see [How to assign device profiles](device-profile-assign.md).

