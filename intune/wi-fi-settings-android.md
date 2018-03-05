---
# required metadata

title: Configure Microsoft Intune Wi-Fi settings for devices running Android 
titleSuffix:
description: Learn Intune  Wi-Fi configuration settings on devices running Android and Android for Work.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Configure Wi-Fi settings in Microsoft Intune for devices running Android and Android for Work  

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This article shows you the Wi-Fi settings you can configure in Microsoft Intune for devices running Android and Android for Work.

## Wi-Fi settings for basic and enterprise profiles

The following Wi-Fi settings are available for both Android and Android for Work devices:

- **Network name** - Enter a name for this Wi-Fi connection. This is the name that users see when they browse the list of available connections on their device.
- **SSID** - Short for service set identifier. This is the real name of the wireless network that devices connect to. However, users only see the network name you configured when they choose the connection.
- **Connect automatically** - Makes the device connect whenever it is in the range of this network.
- **Hidden network** - Prevents this network from being shown in the list of available networks on the device.


## Wi-Fi settings for enterprise profiles only

- **EAP type** - Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections from:
	- **EAP-TLS**
	- **EAP-TTLS**
	- **PEAP**

### Further options when you choose an EAP type

#### Server Trust



|Setting name|More information|Use when|
|-------------|---------------|-----------|
|**Certificate server names**|Specify one or more common names used in the certificates issued by your trusted certificate authority (CA). If you provide this information, you can bypass the dynamic trust dialog that is displayed on user's devices when they connect to this Wi-Fi network.|EAP type is **EAP-TLS** or **EAP-TTLS**|
|**Root certificate for server validation**|Choose the trusted root certificate profile used to authenticate the connection. |EAP type is **EAP-TLS**, **EAP-TTLS**, or **PEAP**|
|**Identity privacy (outer identity)**|Specify the text sent in response to an EAP identity request. This text can be any value. During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.|EAP type is **PEAP**|


#### Client Authentication


|Setting name|More information|Use when|
|----------|--------------|----------|
|**Client certificate for client authentication (Identity certificate)**|Choose the SCEP or PKCS certificate profile used to authenticate the connection.|EAP type is **EAP-TLS**|
|**Authentication method**|Select the authentication method for the connection:<br>- **Certificates** to select the SCEP or PKCS the client certificate that is the identity certificate presented to the server.<br><br>- **Username and Password** to specify a different method for authentication. <br><br>If you selected **Username and Password**, configure:<br><br>-  **Non-EAP method (inner identity)**, then select how you authenticate the connection from:<br>- **None**<br>- **Unencrypted password (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Version 2 (MS-CHAP v2)**<br>The available options depend on the EAP type you selected.<br><br>**and**<br><br>- **Identity privacy (outer identity)** - Specify the text sent in response to an EAP identity request. This text can be any value. During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.|EAP type is **EAP-TTLS** or **PEAP**|
