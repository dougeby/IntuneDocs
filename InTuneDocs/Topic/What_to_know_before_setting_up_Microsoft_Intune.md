---
title: What to know before setting up Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
author: Staciebarker
---
# What to know before setting up Microsoft Intune
Before you set up [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)], you might want to review [Start using Microsoft Intune](../Topic/Start_using_Microsoft_Intune.md). After you are familiar with the capabilities of [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you should be ready to set up your subscription. If you start with a trial subscription, at a later time you can convert it to a full subscription. To convert a trial subscription, see [How to buy Intune](http://technet.microsoft.com/library/dn646949.aspx).

This topic includes information about:

-   [Supported browsers](http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers)

-   [Administrative accounts and permissions for separate tasks](http://technet.microsoft.com/library/dn646966.aspx#BKMK_AdminAccounts)

-   [Web-based portals for administrative tasks](http://technet.microsoft.com/library/dn646966.aspx#BKMK_AdminWebsites)

-   [Company Portal website or app for users](http://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal)

-   [How Intune interacts with other Microsoft services](http://technet.microsoft.com/library/dn646966.aspx#BKMK_ServiceIntegration)

-   [How Intune interacts with other Microsoft products](http://technet.microsoft.com/library/dn646966.aspx#BKMK_ProdcutIntegration)

-   [The amount of network bandwidth use you can expect](http://technet.microsoft.com/library/dn646966.aspx#BKMK_NetworkBandwidth)

-   [Choosing a domain name you will use](http://technet.microsoft.com/library/dn646966.aspx#BKMK_DomainNames)

-   [How Intune maintains security of your data](http://technet.microsoft.com/library/dn646966.aspx#BKMK_DataSecurity)

For requirements about firewalls, ports, domains, proxy servers, On-Premises Connector, and Service to Service Connector, see [Network infrastructure requirements](https://technet.microsoft.com/library/dn646950.aspx).

## Core concepts in Microsoft  Intune
Intune has the following general capabilities:

-   **Manage mobile devices and computers, no servers or intranet required.** You can manage mobile devices and computers, even if those devices are not joined to a domain or brought on-site. This makes [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] ideal for a company with a mobile or geographically-distributed workforce.

-   **Require encryption of mobile devices and computers.** Mobile devices that support encryption can be required to use it. You can also require computers that support Bitlocker drive encryption to use it. If a mobile device or computer with encryption is lost or stolen, the data on the device’s storage media is unreadable, helping to secure that data it from theft.

-   **Generate hardware and software inventories and reports.** You can gather information on the hardware and software used by your company, helping you to plan your hardware upgrade cycle or determine if unwanted software is installed on managed devices.

-   **Monitor mobile devices and computers.** You can create alerts to notify you when there is a problem with a mobile device or a computer, and also have alerts trigger e-mail notifications so that the right people are informed of the problem.

-   **Provide a “self-service” model for IT.** Users can use the Company Portal to enroll devices, to install site-licensed software, or to find contact information for IT administrators.

-   **Support multi-factor authentication.** [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] now supports multi-factor authentication. For details, see [Protect Windows devices with multi-factor authentication](../Topic/Protect_Windows_devices_with_multi-factor_authentication.md).

-   **Available in multiple languages.** Intune is now available in the following languages: Chinese (Simplified and Traditional), Czech, Danish, Dutch, English, Finnish, French, German, Greek, Hungarian, Italian, Japanese, Korean, Norwegian, Polish, Portuguese, Romanian, Russian, Spanish, Swedish, Turkish.  For a list of the countries where the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service is supported, see [International availability](https://products.office.com/en-us/business/international-availability).

## <a name="BKMK_SupportedBrowsers"></a>Web browser requirements
The following web browsers are supported.

|Intune feature |Supported browsers|  
|---------|---------|
|Intune Admin console     |  Internet Explorer 10 or later<br /><br />Google Chrome (versions prior to version 42)<br /><br />Mozilla Firefox <br /><br />**Note:** Edge is currently not supported for the Admin console.   |                           
|Intune Account portal     | Internet Explorer 10 or later<br /><br />Google Chrome <br /><br />Mozilla Firefox<br /><br />**Note:** If you are using the Office 365 Admin Portal, which is replacing the Intune Account portal, see "Office 365 Admin Portal" below for the list of browsers.    
|Office 365 Admin Portal     |Internet Explorer 10 or later<br /><br />Google Chrome<br /><br />Mozilla Firefox <br /><br />Microsoft Edge  |
|Company Portal website     |**On mobile devices:** use the default web browser for each supported platform   <br /><br />**On Windows PCs:** Internet Explorer 10 or later, or Microsoft Edge<br /><br />**On Mac OS X 10.9 or later:** Apple Safari    |

## <a name="BKMK_AdministrativeTasks"></a>How Intune divides administrative tasks
You use two types of administrator accounts, user accounts with additional permissions, and two separate administration consoles to grant your admins access to the things they should manage. The following sections explain these accounts and portals.

### <a name="BKMK_AdminAccounts"></a>Intune administrator accounts and special permissions

|Account type|Permission levels|More information|
|----------------|---------------------|--------------------|
|**Tenant administrator**|Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage.<br /><br />Administrator roles are common between the different Microsoft cloud services although some services might not support some roles. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] uses the following roles:<br /><br />**Global administrator**<br /><br />**Billing administrator**<br /><br />**Password administrator**<br /><br />**Service support administrator**<br /><br />**User management administrator**<br /><br />Learn more about administrator roles: [Reference for Tenant Administrator accounts for Microsoft Intune](../Topic/Reference_for_Tenant_Administrator_accounts_for_Microsoft_Intune.md).<br /><br />[Assign administrative users](http://technet.microsoft.com/library/dn646983.aspx#BKMK_AssignAdmins).|By default, the account you use to create your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] subscription is a tenant administrator with the global administrator role.<br />                        **As a tenant administrator, you use the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)] to manage your subscription for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].** and assign tenant administrators from within the [!INCLUDE[wit_icp_2](../Token/wit_icp_2_md.md)].<br /><br />Use a tenant administrator with the global administration role to access the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to access the [!INCLUDE[wit_icp_2](../Token/wit_icp_2_md.md)].<br /><br />The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], your service is a [tenant of Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx).|
|**Service administrator**|Service administrators are assigned one of the following permissions:<br /><br />**Full access**: Grants access to all areas of the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], with no restrictions. Can also add and manage other service administrators.<br /><br />**Read-only access**: Grants read permission to all areas of the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)]. A read-only service admin cannot modify data, but can run reports.<br /><br />**Helpdesk - Groups Node**: Grants permissions that enable the service administrator to only perform a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see [Control what admins can see in the Microsoft Intune admin console](../Topic/Control_what_admins_can_see_in_the_Microsoft_Intune_admin_console.md).<br /><br />[Assign administrative users](http://technet.microsoft.com/library/dn646983.aspx#BKMK_AssignAdmins)|By default, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. **As a service administrator, you use the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] to manage day-to-day tasks for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]**.<br /><br />You assign service administrators from within the administrator console. A service administrator requires a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] before the account can access the administration console.|
|**Device enrollment manager**|Device enrollment managers are standard user accounts that have additional permission to enroll more than five devices.<br /><br />[Learn about device enrollment managers](http://technet.microsoft.com/library/dn764961.aspx).|By default, each [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] user can enroll up to five devices.<br /><br />However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or serve in a kiosk mode where a user to device association is not required.|

### <a name="BKMK_AdminWebsites"></a>Administrative websites for Intune
Different administrative tasks require you to use one of two administrative websites. Because the configurations you make and data from devices that you manage are stored in the cloud, you can manage your subscription from any computer with [a supported browser](http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers).

|Administrative website|More information|
|--------------------------|--------------------|
|[Microsoft Intune account portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)|**As a tenant administrator, use this portal to manage your subscription**, including the following tasks when permitted by your administrator role:<br /><br />Manage user accounts for the subscription and configure directory synchronization from your on-premises Active Directory.<br /><br />Manage groups of users, called security groups.<br /><br />Assign licenses to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to users.<br /><br />Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with.<br /><br />Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.<br /><br />Find links to view the health of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.<br /><br />As a tenant administrator, you can sign in to the account portal to manage the subscription even when your account is not assigned a license to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].<br /><br />Any user who has a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] but is not an administrator can use this portal to reset their account password and edit their profile.<br /><br />To access the account portal, your account must have a sign-in status of **Allowed**. This status is distinct from being granted a license to the subscription. By default, all user accounts are **Allowed**.<br /><br />Learn more about [adding users and assigning licenses for your subscription](http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses).|
|[Microsoft Intune administrator console](https://admin.manage.microsoft.com/)|**As a service administrator, use this portal to manage day-to-day operations** including:<br /><br />Set policies for computers and mobile devices.<br /><br />Upload and deploy software like software updates and apps.<br /><br />Manage [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Endpoint Protection on computers.<br /><br />View device status and run reports.<br /><br />A user who does not have service administrator permissions cannot sign in to this portal. An exception to this restriction is a user who is a tenant administrator with the global administrator role.<br /><br />To access the administration console, your account must have a license to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and a sign-in status of **Allowed**. By default, all user accounts are set to **Allowed**.<br /><br />Learn more about [adding users and assigning licenses for your subscription](http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses).|

## <a name="BKMK_CompanyPortal"></a>Microsoft Intune company portal
The [!INCLUDE[wit_iwportal_1](../Token/wit_iwportal_1_md.md)] provides users access to company data and apps. Users can access the company portal by using:

-   **The company portal app**: An application that is available on devices you manage with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. This company portal is also called a self-service portal.

-   **The company portal website**: A website that provides access from [a supported browser](http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers).

Users can use the [!INCLUDE[wit_iwportal_2](../Token/wit_iwportal_2_md.md)] to:

-   Enroll devices

-   View the status of their devices

-   Download software that is deployed by your organization

-   Contact your IT department for support

Before a user can access the [!INCLUDE[wit_iwportal_2](../Token/wit_iwportal_2_md.md)], the user’s account must be granted a license to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and have a sign-in status of **Allowed**. Learn more about [adding users and assigning licenses for your subscription](http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses).

Following is the ULR for the company portal website. When users sign in, they gain access to your company portal website.

-   [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)

Learn more about [ customizing the company portal](http://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).

## <a name="BKMK_ServiceIntegration"></a>Integration with other Microsoft cloud services
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] shares a common foundation with other Microsoft cloud services. When you use the same account to subscribe to multiple cloud services, those services use the same Microsoft Azure AD infrastructure, and they are tenants of Azure AD. Azure AD provides the core directory and identity management capabilities for Microsoft cloud services.

Learn more about [administering Azure AD ](http://technet.microsoft.com/library/hh967611.aspx) in the TechNet Library.

## <a name="BKMK_ProdcutIntegration"></a>Integration with other Microsoft products
You can use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] as a stand-alone cloud service or as a cloud service that is integrated with other products. Presently, only [!INCLUDE[cmshort](../Token/cmshort_md.md)] can be integrated directly with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

The decision to integrate [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] with [!INCLUDE[cmshort](../Token/cmshort_md.md)] is a permanent choice that requires you to set the mobile device management authority from the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console and not from within the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)]. After the mobile device management authority is set, you cannot change or reverse this configuration.

When you use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] with [!INCLUDE[cmshort](../Token/cmshort_md.md)], you do not use the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] to manage [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and instead use the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] still uses its cloud storage in Azure to host software that you deploy to devices that you manage with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

For more information, see [Manage Mobile Devices with Configuration Manager and Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) in the [!INCLUDE[cm5short](../Token/cm5short_md.md)] SP1 documentation.

## <a name="BKMK_NetworkBandwidth"></a>Network bandwidth use
Use the information in the following sections to plan for network traffic for [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] clients.

### <a name="BKMK_AverageTraffic"></a>Average network traffic
The following table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure that computers and mobile devices receive the necessary updates and content from the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service, they must be periodically connected to the Internet. The time taken to receive updates or content will vary, but as a guideline, they should remain continuously connected to the Internet for at least 1 hour each day.

|Content type|Approximate size|Frequency and details|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client installation<br /><br />**The following requirements are in addition to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client installation**|125 MB|**One time**<br /><br />The size of the client download varies depending on the operating system of the client computer.|
|Client enrollment package|15 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Endpoint Protection agent|65 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Operations Manager agent|11 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Policy agent|3 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Remote Assistance via Microsoft Easy Assist agent|6 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Daily client operations|6 MB|**Daily**<br /><br />The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client regularly communicates with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service to check for updates and policies, and to report the client’s status to the service.|
|Endpoint Protection malware definition updates|Varies<br /><br />Typically 40 KB to 2 MB|**Daily**<br /><br />Up to three times a day.|
|Endpoint Protection engine update|5 MB|**Monthly**|
|Software updates|Varies<br /><br />The size depends on the updates you deploy.|**Monthly**<br /><br />Typically, software updates release on the second Tuesday of each month.<br /><br />A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.|
|Service packs|Varies<br /><br />The size varies for each service pack you deploy.|**Varies**<br /><br />Depends on when you deploy service packs.|
|Software distribution|Varies<br /><br />The size depends on the software you deploy.|**Varies**<br /><br />Depends on when you deploy software.|

#### <a name="BKMK_ReduceBandwidth"></a>Reduce network bandwidth use
You can use one or more of the following methods to reduce network bandwidth use for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients.

##### <a name="BKMK_UseProxy"></a>Use a proxy server to cache content requests
You can use a proxy server that can cache content to reduce duplicate downloads and reduce the use of network bandwidth by clients that request content from the Internet.

A caching proxy server receives requests for content from client computers on your network, retrieves that content from the Internet, and can then cache both HTTP responses and binary downloads. The server uses the cached information to answer subsequent requests from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client computers.

The following are typical settings to use for a proxy server that caches content for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients.

|Setting|Recommended value|Details|
|-----------|---------------------|-----------|
|Cache size|5 GB to 30 GB|The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment.|
|Individual cache file size|950 MB|This setting might not be available in all caching proxy servers.|
|Object types to cache|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.|
For information about using a proxy server to cache content, see the documentation for your proxy server solution.

##### <a name="BKMK_UseBITS"></a>Use Background Intelligent Transfer Service on computers
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] supports using Background Intelligent Transfer Service (BITS) on a Windows computer to reduce the network bandwidth that is used during the hours that you configure. You can configure policy for BITS on the **Network bandwidth** page of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Agent policy.

To learn more about BITS and Windows computers, see [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in the TechNet Library.

##### <a name="BKMK_UseBrancCache"></a>Use BranchCache on computers
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems that are supported as clients also support BranchCache:

-   [!INCLUDE[nextref_client_7](../Token/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

By default, BranchCache and distributed cache mode are enabled on a computer when the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client is installed. However, if the client already has Group Policy that disables BranchCache, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not override that policy and BranchCache will remains disabled on that computer.

If you use BranchCache, you should communicate with other administrators in your organization who manage Group Policy and [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Firewall policy to ensure they do not deploy policy that disables BranchCache or Firewall exceptions.

Learn more: [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="BKMK_DomainNames"></a>Domain names for Microsoft Intune
When your organization signs up for a cloud-based service from Microsoft like [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)], you’re given an initial domain name that looks like the following: **contoso.onmicrosoft.com**. In this example, **contoso** is the domain name that you chose when you signed up, and **onmicrosoft.com** is the suffix assigned to accounts you add to your subscription. After you complete the sign-up process, you cannot change that domain name. However, as a global administrator, you can add your own custom domain names for your organization to use with the service, or you can remove domains that you’ve added previously.

By default, when you use the onmicrosoft domain, each user you import receives the **onmicrosoft.com** suffix for their user principal name (UPN).

If you want to use a domain name that you own rather than the one that you were given at signup, you can add the domain name to Azure AD. After you add the domain, and it has been verified that you own it, you can create accounts and groups that include the domain name by changing DNS resource records at your DNS hosting provider. To simplify management of user accounts when you plan to use a custom domain, [Step 2: Configure a custom domain name](../Topic/Get_started_with_a_paid_subscription_to_Microsoft_Intune.md#BKMK_ConfigureDomain) to your subscription before you begin to synchronize users from your local Active Directory.

Because the information about configuring domain names and DNS resource records for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is the same as for other Azure AD tenants, use the information and procedures found under [Internet domain management](http://technet.microsoft.com/library/hh969248.aspx), which include:

-   [Add your domain](http://technet.microsoft.com/library/hh969247.aspx)

-   [DNS Basics](http://technet.microsoft.com/library/jj151795.aspx)

-   [Locate your domain services or buy a new domain](http://technet.microsoft.com/library/jj151801.aspx)

-   [Work with domain names and DNS records](http://technet.microsoft.com/library/jj151817.aspx)

-   [Verify a domain](http://technet.microsoft.com/library/jj151788.aspx)

-   [Troubleshoot issues after changing your domain name](http://technet.microsoft.com/library/jj151793.aspx)

After you review the information about domains and DNS resource records, return to this topic to continue learning about [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

## <a name="BKMK_DataSecurity"></a>Data security with Microsoft Intune
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is a cloud-based service where the infrastructure that hosts your data is managed for you in Azure datacenters. The cloud-based storage of data can raise a number of questions that often include the following:

-   Who has access to the data?

-   Where does [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] store data when using Microsoft Azure?

-   How is data secured, including transfer between clients, web consoles, and the cloud?

-   How is the privacy of data assured?

-   Who owns the data?

-   Is there any third-party verification?

These and additional data security questions are answered in the [Microsoft Intune Privacy and Data Protection Overview](http://go.microsoft.com/fwlink/?LinkId=528219) white paper.

## See Also
[Introduction to Microsoft Intune](../Topic/Introduction_to_Microsoft_Intune.md)
[Network infrastructure requirements for Microsoft Intune](../Topic/Network_infrastructure_requirements_for_Microsoft_Intune.md)

