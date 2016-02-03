---
title: Understand your devices with inventory in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
author: robstackmsft
---
# Understand your devices with inventory in Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] lets you view the inventory of enrolled devices and Windows PCs that run the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software.

## What's collected from enrolled devices?
To view the inventory collected by mobile devices, run the [Mobile Device Inventory Reports](https://technet.microsoft.com/library/dn646977.aspx). [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] collects the following inventory from mobile devices:

|Property|Exchange ActiveSync|iOS|Mac OS X|Android|Windows RT and Windows 8.1|Windows Phone 8 and Windows Phone 8.1|Windows 10|Notes|
|------------|-----------------------|-------|------------|-----------|------------------------------|-----------------------------------------|--------------|---------|
|**Name**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Operating System**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Manufacturer**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Model**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Management Channel**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**AAD Registered**|Yes|Yes|No|Yes|Yes|Yes|Yes||
|**Compliant**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**EAS Activated**|Yes|Yes|No|Yes|Yes|Yes|Yes||
|**EAS Activation ID**|Yes|Yes|No|Yes|Yes|Yes|Yes||
|**EAS Activation Time**|Yes|Yes|No|Yes|Yes|Yes|Yes||
|**Management State**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Email Address**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Exchange ActiveSync ID**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Jailbroken or Rooted**|No|Yes|No|Yes|No|No|No||
|**Unique Device ID**|No|Yes|Yes|Yes|Yes|Yes|Yes||
|**Serial number**|No|Yes|Yes|Yes|Yes|No|Yes||
|**Total Storage Space**|No|Yes|Yes|No|Yes|No|Yes||
|**Free Storage Space**|No|Yes|Yes|No|Yes|No|Yes||
|**Phone Number**|No|Yes|No|Yes|No|Yes|No|Phone number is masked with &#42; except for the last 4 digits.|
|**IMEI**|Yes|Yes|No|Yes|No|Yes|No||
|**MEID**|No|Yes|No|No|No|No|No|Mobile Equipment Identifier|
|**Wi-Fi MAC**|No|Yes|Yes|Yes|Yes|Yes|Yes||
|**Subscriber Carrier**|No|Yes|No|Yes|No|No|No||
|**Cellular Technology**|No|Yes|No|Yes|No|No|No||
|**Supervised**|No|Yes|No|No|No|No|No||
|**Activation Lock State**|No|Yes|No|No|No|No|No||
|**Enrolled Date**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Last Updated**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||
|**Ethernet MAC**|No|No|Yes|No|No|No|No||
|**Activation Lock Enabled**|No|Yes|No|No|No|No|No||
|**Encryption Enabled**|Yes|Yes|Yes|Yes|Yes|Yes|Yes||

## What's collected from Windows PCs
> [!IMPORTANT]
> This section applies only to Windows PCs that run the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] computer client software.

To view the inventory collected by Windows PCs, run the [Computer Inventory Reports](https://technet.microsoft.com/library/dn646977.aspx). [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] collects the following inventory from Windows PCs:

-   **Name**

-   **Chassis Type**

-   **Manufacturer**

-   **Model**

-   **Operating System**

-   **TPM Version**

-   **Total Disk Space**

-   **Used Disk Space**

-   **Free Disk Space**

-   **OS Disk Name**

-   **OS Disk Space**

-   **OS Disk Free Space**

-   **Physical Memory**

-   **Processor Name**

-   **Processor Architecture**

-   **CPU Speed**

-   **IP Address**

-   **Serial number**

-   **Last User to Log On**

-   **Assigned User**

-   **Last Updated**

## See Also
[Monitoring and reports with Microsoft Intune](../Topic/Monitoring_and_reports_with_Microsoft_Intune.md)

