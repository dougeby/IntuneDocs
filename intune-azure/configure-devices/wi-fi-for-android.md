---
# required metadata

title: Intune Wi-Fi settings for Android devices | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wi-Fi for Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## Wi-Fi settings for basic and enterprise profiles

- **Network name** - Enter a name for this Wi-Fi connection. This is the name that users will see when they browse the list of available connections on their device.
- **SSID** - Short for service set identifier. This is the real name of the wireless network that devices will connect to. However, users only see the network name you created above when they choose the connection.
- **Connect automatically** - Makes the device connect whenever it is in the range of this network. 
- **Hidden network** - Prevents this network from being shown in the list of available networks on the device.


## Wi-Fi settings for enterprise profiles only

- **EAP type** - Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections from:
	- **EAP-TLS**
	- **EAP-TTLS**
	- **PEAP**

### Further options when you choose an EAP type

#### Server Trust

||||
|-|-|-|
|Setting name|More information|Use when:|
|**Certificate server names**|-|EAP type is **EAP-TLS** or **EAP-TTLS**|
|**Root certificate for server validation**|-|EAP type is **EAP-TLS**, **EAP-TTLS**, or **PEAP**|
|**Identity privacy (outer identity)**|-|EAP type is **PEAP**|


#### Client Authentication

||||
|-|-|-|
|Setting name|More information|Use when:|
|**Client certificate for client authentication (Identity certificate)**|-|EAP type is **EAP-TLS**|
|**Authentication method**|-|EAP type is **EAP-TTLS** or **PEAP**|