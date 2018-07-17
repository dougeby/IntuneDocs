---
# required metadata

title: View device details with Microsoft Intune - Azure | Microsoft Docs
description: View your device details, including operating systems, storage space, manufacturer, and model. Get a list of installed apps, check compliance policies, and set up TeamViewer with Microsoft Intune in Azure. Similar to viewing inventory of the devices you manage.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: dougeby
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# See device details in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

The **Devices** feature provides additional details into the devices you manage, including their hardware and the apps installed.

This article shows you how to view all your devices, and their properties in the Azure portal.

## View the device details

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices** > **All devices** > select one of your listed devices to open its details:

   - **Overview** shows the device name, and lists some key properties of the device, including whether it's a bring-your-own-device (BYOD) device, when it checked in, and more. Select **More** to:
     - Remove company data
     - Delete the device
     - Remote lock the device
     - Erase
     - Start a remote assistance session
   - Use **Properties** to assign a [device category you create](device-group-mapping.md), and change ownership of the device to a personal device, or a corporate device.
   - **Hardware** includes many details about the device, including the device ID, the operating system and version, storage space, the model and manufacturer, conditional access settings, and more details.
   - **Discovered apps** lists all the apps that Intune found installed on the device, and the app versions. You can also **Export** the app list into a .csv file.
   - **Device compliance** lists all assigned compliance policies, and if the device is compliant or not compliant.
   - **Device configuration** shows all device configuration policies assigned to the device, and if the policy succeeded or failed.

Intune collects an app list only on corporate-owned devices. Apps aren't checked on personal devices. For Windows 10 PCs, only modern apps are listed for corporate-owned devices. Intune doesn't collect information about Win32 apps on the device. Depending on the carrier used by the devices, not all apps might be collected.

|Platform|For Personal-owned Devices|For Company-owned devices|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (without the Configuration Manager client)|Only managed apps|Only managed apps|
|Windows 8.1 (without the Configuration Manager client)|Only managed apps|Only managed apps|  
|Windows Phone 8|Only managed apps|Only managed apps|  
|Windows RT|Only managed apps|Only managed apps|  
|iOS|Only managed apps|All apps installed on the device|
|macOS|All apps installed on the device|All apps installed on the device|  
|Android|Only managed apps|All apps installed on the device|  

## Hardware device details

### Windows and iOS device details:
|Detail|Description|  
|--------------|----------------------|  
|Name|The name of the device.|
|Management name|The device name used only in the console. Changing this name won't change hte name on the device.|
|UDID|The device's Unique Device identifier.|
|Intune Device ID|A GUID that uniquely identifies the device.|
|Serial number|The device's serial number from the manufacturer.|
|Shared device|If **Yes**, the device is shared by more than one user.|
|User approved enrollment|If **Yes**, then the device has user approved enrollment which lets admins manage certain security settings on the device.|
|Operating system|The operating system used on the device.|
|Operating system version|The version of the operating system on the device.|
|Operating system language|The language set for the operating system on the device.|
|Total storage space|The total storage space on the device (in gigabytes).|
|Free storage space|The unused storage space on the device (in gigabytes).|


### Windows, iOS, and macOS device details
|Detail|Description|  
|--------------|----------------------|  
|IMEI|The device's International Mobile Equipment Identity.|
|MEID|The device's mobile equipment identifier.|
|Manufacturer|The manufacturer of the device.|
|Model|The model of the device.|
|Phone number|The phone number assigned to the device.|
|Subscribe carrier|The device's wireless carrier.|
|Cellular technology|The radio system used by the device.|
|Wi-Fi MAC|The device's Media Access Control address.|
|ICCID|The Integrated Circuit Card Identifier, which is a SIM card's unique identification number.|
|Enrolled date|The date and time that the device was enrolled in Intune.|
|Last contact|The date and time that the device last connected to Intune.|
|Activation lock bypass code|The code that can be used to bypass the activation lock.|
|Azure AD registered|If **Yes**, the device is registered with Azure Directory.|
|Compliance|The device's compliance state.|
|EAS activated|If **Yes**, then the device is synchronized with an Exchange mailbox.|
|EAS activation ID|The device's Exchange ActiveSync identifier.|
|Supervised|If **Yes**, administrators have enhanced control over the device.|
|Encrypted|If **Yes**, the data stored on the device is encrypted.|



## Next steps
See what else you can do to [manage your devices](device-management.md) with Intune.