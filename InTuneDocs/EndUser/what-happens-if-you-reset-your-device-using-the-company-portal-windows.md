---
# required metadata

title: What happens if you reset your device using the Company Portal? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# What happens if you reset your device using the Company Portal?

When you use the Company Portal app or [Company Portal website](reset-your-device-cpwebsite.md) to reset your Windows device, it resets your device to its factory settings, and deletes all apps, settings, and data, including your personal data. What happens on each device depends on the type of device you have and how you are using the device, as described in the following table. For instructions on how to reset your lost or stolen device, see [Reset (erase) your lost or stolen device](reset-erase-your-lost-or-stolen-device-windows.md).

|Device configuration and management|Device type|
|---------------------------------------|---------------|
|Your IT admin manages your mobile device|**Windows 10, Windows Phone 8.1 and Windows Phone 8**</br>Your device won’t appear in the company portal anymore and the company portal tries to reset the device back to the manufacturer’s default settings. Your personal data, apps and settings will be removed. <br /><br />**Windows 10 Mobile**: the only way to unenroll your device is to reset it.<br /><br />**Windows RT**<br />You cannot reset a Windows RT device unless it is used for email only.|
|Your device can access company email only|**Windows Phone 8.1 and Windows Phone 8**<br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**Windows RT**<br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**Windows 7 or Windows Vista Computers**<br />You cannot reset a computer that is running Windows 7 or earlier that is used for email only.<br /><br />**Windows 8.1 and Windows 8 Computers**<br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.|
|PCs and laptops|**Windows 8.1 and Windows 8 Computers**<br />You cannot reset a computer that is running Windows 8 or Windows 8.1 unless it is used for email only.<br /><br />**Windows 7 or Windows Vista Computers**<br />You cannot reset a computer that is running Windows 7 or earlier.|

If you have questions, contact your IT administrator. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

### See also
[Using your Windows device with Intune](using-your-windows-device-with-intune.md)