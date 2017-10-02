---
# required metadata

title: Intune AirPlay settings for iOS devices
titlesuffix: "Azure portal"
description: "Learn how you can use Intune to help automatically connect iOS devices to AirPlay compatible devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
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

# Intune AirPlay settings for iOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings to help connect iOS devices you manage to AirPlay compatible devices (like Apple TVs) on your network.
With this capability you can:

- **Configure a device and password list** - Let users automatically connect to AirPlay devices that are in range. Provision them with the name and password of AirPlay devices so that they don't need to supply it when they connect.
- **Configure allowed destinations** - Configure a list of AirPlay devices (by device ID). End users can only see and connect to the devices you list (for supervised devices only).

## Get started

1. On the **Device features** blade, choose **AirPlay**.
2. On the **AirPlay** blade, choose one or both of the following actions:

## Configure a device and password list

1. On the **Passwords** blade, enter the **Device Name** and **Password** of an AirPlay device, for example **Contoso Apple TV**.
2. After entering the device details, click **Add**. The device appears in the **Device Name** list.
3. Continue to add devices. When you are finished, choose **OK**.


## Configure allowed destinations

1. On the **Allowed destinations (supervised only)** blade, enter the **Device ID** of an AirPlay device, for example 52:46:CD:51:83:4C.
2. After entering the device ID, click **Add**. The ID appears in the **Device ID** list.
3. Continue to add devices. When you are finished, choose **OK**.

You can also import device and passwords, and allowed destinations from a comma-separated values (csv) file.


## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).

