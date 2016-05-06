---
# required metadata

title: Understand your devices with inventory in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Understand your devices with inventory in Microsoft Intune
Microsoft Intune lets you view the inventory of enrolled devices and Windows PCs that run the Intune client software.

## What's collected from enrolled devices?
To view the inventory collected by mobile devices, run the [Mobile Device Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md). Intune collects the following inventory from enrolled devices:

|Property|Collected by|
|------------|-----------------------|
|**Name**|All devices|
|**Operating System**|All devices|
|**Manufacturer**|All devices|
|**Model**|All devices|
|**Management Channel**|All devices|
|**AAD Registered**|All devices except Mac OS X|
|**Compliant**|All devices|
|**EAS Activated**|All devices except Mac OS X|
|**EAS Activation ID**|All devices except Mac OS X|
|**EAS Activation Time**|All devices except Mac OS X|
|**Management State**|All devices|
|**Email Address**|All devices|
|**Exchange ActiveSync ID**|All devices|
|**Jailbroken or Rooted**|iOS and Android devices only|
|**Unique Device ID**|All devices except Exchange ActiveSync|
|**Serial number**|iOS, Mac OS X, Android, Windows 8.1, Windows 10 devices|
|**Total Storage Space**|iOS, Mac OS X, Windows 8.1, Windows 10 devices|
|**Free Storage Space**|iOS, Mac OS X, Windows 8.1, Windows 10 devices|
|**Phone Number**<br>Phones categorized as corporate are identified with their full phone number, for example, when you run a mobile device inventory report. BYOD phone numbers are masked with &#42;, with only the last 4 digits displayed.|iOS, Android, and Windows Phone devices|
|**IMEI**|Exchange ActiveSync, iOS, Android, and Windows Phone devices|
|**MEID**<br>Mobile Equipment Identifier|iOS devices only|
|**Wi-Fi MAC**|All devices except Exchange ActiveSync|
|**Subscriber Carrier**|iOS and Android devices only|
|**Cellular Technology**|iOS and Android devices only|
|**Supervised**|iOS devices only|
|**Activation Lock State**|iOS devices only|
|**Enrolled Date**|All devices|
|**Last Updated**|All devices|
|**Ethernet MAC**|Mac OS X devices only|
|**Activation Lock Enabled**|iOS devices only|
|**Encryption Enabled**|All devices|

## What's collected from Windows PCs
> [!IMPORTANT]
> This section applies only to Windows PCs that run the Intune Windows PC client software.

To view the inventory collected by Windows PCs, run the [Computer Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md). Intune collects the following inventory from Windows PCs:

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

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
