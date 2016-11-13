---
# required metadata

title: Intune Wi-Fi settings for macOS devices | Microsoft Docs
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
ms.assetid: 322a38d5-21f5-48ee-bc59-0a4f9da78d38

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wi-Fi settings for macOS devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## Wi-Fi settings for basic and enterprise profiles

- **Network name** - Enter a name for this Wi-Fi connection. This is the name that users will see when they browse the list of available connections on their device.
- **SSID** - Short for service set identifier. This is the real name of the wireless network that devices will connect to. However, users only see the network name you created above when they choose the connection.
- **Connect automatically** - Makes the device connect whenever it is in the range of this network. 
- **Hidden network** - Prevents this network from being shown in the list of available networks on the device.
- **Proxy settings** - Choose from:
	- **None** - No proxy settings will be configured.
	- **Manual** - Enter the **Proxy server address** (as an IP address), and it's associated **Port number**.
	- **Automatic** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.

## Wi-Fi settings for basic profiles only

- **Security type** - 

## Wi-Fi settings for enterprise profiles only

- **EAP type** - 

