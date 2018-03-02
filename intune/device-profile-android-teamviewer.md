---
# required metadata

title: Remotely administer devices in Microsoft Intune - Azure | Microsoft Docs
description: View the required roles to use TeamViewer, how to install the TeamViewer connector, and step-by-step guidance to remotely administer devices using Microsoft Intune in the Azure portal
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Use TeamViewer to remotely administer InTune devices

Devices managed by InTune can be administered remotely using [TeamViewer](https://www.teamviewer.com). TeamViewer is a 3rd party program that you purchase separately. This topic shows you how to configure TeamViewer within InTune, and to remotely administer a device. 

## Prerequisites

- Use a supported device. Intune-managed Android and Windows devices support remote administration. TeamViewer may not support Windows Holographic (HoloLens), Windows Team (Surface Hub), or Windows 10 S. For supportability, we suggest referring to [TeamViewer](https://www.teamviewer.com) for any updates.

- The InTune administrator within the Azure portal must have following [Intune roles](role-based-access-control.md):  

    - **Update Remote Assistance**: Allows administrators to modify the TeamViewer connector settings
    - **Request Remote Assistance**: Allows administrators to start a new remote assistance session for any user. Users with this role are not limited by any InTune role within a scope. Also, user or device groups assigned an InTune role within a scope can also request remote assistance. 

- Download and install [TeamViewer](https://www.teamviewer.com). 

By enabling TeamViewer, you are allowing the TeamViewer for Intune Connector to create TeamViewer sessions, read Active Directory data, and save the TeamViewer account access token.

## Configure the TeamViewer connector

To provide remote assistance to devices, configure the Intune TeamViewer connector using the following steps:

1. In the [Azure portal](https://portal.azure.com), select **All Services**, and search for **Microsoft Intune**.
2. In **Microsoft Intune**, select **Devices**, and then select **TeamViewer Connector**.
3. Select **Connect**, and then accept the license agreement.
4. Select **Log in to TeamViewer to authorize**.
5. A web page opens to the TeamViewer site. Enter your TeamViewer license credentials, and then **Sign In**.

## Remotely administer a device

After the connector is configured, you're ready to remotely administer a device. Use the following steps: 

1. In the [Azure portal](https://portal.azure.com), select **All Services**, and search for **Microsoft Intune**.
2. In **Microsoft Intune**, select **Devices**, and then select **All devices**.
3. From the list, select the device that you want to remotely administer. In the device properties, select **New Remote Assistance Session**.
4. After Intune connects to the TeamViewer service, you'll see some information about the device. **Connect** to start the remote session.

![Use TeamViewer to remotely administer Android device - example](./media/android-teamviewer.png)

When you start a remote session, an end user sees a notification flag on the Company Portal app icon on their device, and also sees a notification when they open the app. The user can then accept the remote assistance request.

In TeamViewer, you can complete a range of actions on the device, including taking control of the device. For full details of what you can do, see the [TeamViewer guidance](https://www.teamviewer.com/support/documents/).

When finished, close the TeamViewer window.