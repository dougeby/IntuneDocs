---
title: Intune network bandwidth use
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: 
ms.assetid: 
author: Staciebarker
---
# Intune network bandwidth use


Before you set up [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)], review this topic and the information in the list below. You might also want to review [Choose how to manage devices with Microsoft Intune](introduction-to-microsoft-intune.md). After you are familiar with the capabilities of [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], you should be ready to set up your subscription. If you start with a trial subscription, you can convert it later to a full subscription (see [How to buy Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/overview.aspx)).

- [General capabilities of Intune](what-to-know-before-setting-up-microsoft-intune.md#BKMK_general_capabilities)
- [Intune supported web browsers](supported-web-browsers.md)
- [Network infrastructure requirements for Microsoft Intune](network-infrastructure-requirements-for-microsoft-intune.md)
- [Administrative accounts, websites, and permissions in Microsoft Intune](administrative-accounts-websites-perms.md)
- [Microsoft Intune Company Portal](microsoft-intune-company-portal.md)
- [Intune integration with Microsoft cloud services and products](integration-with-cloud-services.md)
- [Domain names for Microsoft Intune](domain-names-for-intune.md)

Use the information in the following sections to plan for network traffic for [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] clients.

## <a name="BKMK_AverageTraffic"></a>Average network traffic
The following table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure that computers and mobile devices receive the necessary updates and content from the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] service, they must be periodically connected to the Internet. The time taken to receive updates or content will vary, but as a guideline, they should remain continuously connected to the Internet for at least 1 hour each day.

|Content type|Approximate size|Frequency and details|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client installation<br /><br />**The following requirements are in addition to the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client installation**|125 MB|**One time**<br /><br />The size of the client download varies depending on the operating system of the client computer.|
|Client enrollment package|15 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Endpoint Protection agent|65 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Operations Manager agent|11 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Policy agent|3 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Remote Assistance via Microsoft Easy Assist agent|6 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Daily client operations|6 MB|**Daily**<br /><br />The [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client regularly communicates with the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] service to check for updates and policies, and to report the client’s status to the service.|
|Endpoint Protection malware definition updates|Varies<br /><br />Typically 40 KB to 2 MB|**Daily**<br /><br />Up to three times a day.|
|Endpoint Protection engine update|5 MB|**Monthly**|
|Software updates|Varies<br /><br />The size depends on the updates you deploy.|**Monthly**<br /><br />Typically, software updates release on the second Tuesday of each month.<br /><br />A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.|
|Service packs|Varies<br /><br />The size varies for each service pack you deploy.|**Varies**<br /><br />Depends on when you deploy service packs.|
|Software distribution|Varies<br /><br />The size depends on the software you deploy.|**Varies**<br /><br />Depends on when you deploy software.|

## <a name="BKMK_ReduceBandwidth"></a>Ways to reduce network bandwidth use
You can use one or more of the following methods to reduce network bandwidth use for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] clients.

### <a name="BKMK_UseProxy"></a>Use a proxy server to cache content requests
You can use a proxy server that can cache content to reduce duplicate downloads and reduce the use of network bandwidth by clients that request content from the Internet.

A caching proxy server receives requests for content from client computers on your network, retrieves that content from the Internet, and can then cache both HTTP responses and binary downloads. The server uses the cached information to answer subsequent requests from [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client computers.

The following are typical settings to use for a proxy server that caches content for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] clients.

|Setting|Recommended value|Details|
|-----------|---------------------|-----------|
|Cache size|5 GB to 30 GB|The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment.|
|Individual cache file size|950 MB|This setting might not be available in all caching proxy servers.|
|Object types to cache|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.|
For information about using a proxy server to cache content, see the documentation for your proxy server solution.

### <a name="BKMK_UseBITS"></a>Use Background Intelligent Transfer Service on computers
[!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] supports using Background Intelligent Transfer Service (BITS) on a Windows computer to reduce the network bandwidth that is used during the hours that you configure. You can configure policy for BITS on the **Network bandwidth** page of the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Agent policy.

To learn more about BITS and Windows computers, see [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in the TechNet Library.

### <a name="BKMK_UseBrancCache"></a>Use BranchCache on computers
[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems that are supported as clients also support BranchCache:

-   [!INCLUDE[nextref_client_7](./includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](./includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](./includes/winblue_client_2_md.md)]

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

By default, BranchCache and distributed cache mode are enabled on a computer when the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client is installed. However, if the client already has Group Policy that disables BranchCache, [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] does not override that policy and BranchCache will remains disabled on that computer.

If you use BranchCache, you should communicate with other administrators in your organization who manage Group Policy and [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] Firewall policy to ensure they do not deploy policy that disables BranchCache or Firewall exceptions. For more about BranchCache, see [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

### See also
[What to know before you start](what-to-know-before-setting-up-microsoft-intune.md)</br>
[Network infrastructure requirements for Microsoft Intune](network-infrastructure-requirements-for-microsoft-intune.md)