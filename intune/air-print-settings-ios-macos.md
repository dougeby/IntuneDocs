---
# required metadata

title: Intune AirPrint settings for iOS and macOS devices
titlesuffix: "Azure portal"
description: Learn how you can use Intune to help automatically connect iOS and macOS devices to AirPrint compatible printers."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# AirPrint settings for iOS and macOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings to configure iOS or macOS devices to automatically connect to AirPrint compatible printers on your network. You need the IP address and resource path of your printers to proceed.

## Find AirPrint printer information

Use this procedure to add AirPrint information to the AirPrint payload so that iOS device users can print to known AirPrint printers.

1. On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open Terminal (from **/Applications/Utilities**)
2. In the Terminal, type **ippfind**, then press enter.
3. Make a note of any printer information the command returns, for example: **ipp://myprinter.local.:631/ipp/port1**. The first part of the information is the name of your printer and the last part is the resource path.
4. In the Terminal, type **ping myprinter.local**, then press enter.
5. Make a note of the IP address information returned by the command, for example, **PING myprinter.local (10.50.25.21)**.
6. Finally, use the IP address and resource path in the AirPrint payload settings. An example IP address might be **10.50.25.21**, and an example resource path might be **/ipp/port1**.

## Configure an AirPrint profile

1. On the **Device features** blade, choose **AirPrint**.
2. On the **AirPrint** blade, to add an AirPrint destination, enter its **IP address** and **resource path**, and then click **Add**.
3. Continue to add as many destinations as you need. When you are finished, choose **OK**.

You can also import a list of printers from a comma-separated values (.csv) file or export the list.


## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).