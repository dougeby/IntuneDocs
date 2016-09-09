---
# required metadata

title: MAM CA overlap with Device CA | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/24/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 111b745f-a04e-4d7c-800c-a27d3da1654b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Overlap between app based conditional access and device based conditional access
Conditional Access for MAM (MAM CA) can be configured to overlap with Conditional Access for devices (Device CA).  Device CA can be configured through the Intune MDM console or the Azure Active Directory Premium console, and will require that users may only connect with SharePoint Online and Exchange Online if they are on managed and compliant devices (or domain joined PCs).  If a user belongs to one or more security groups that are targeted in both a MAM CA and a Device CA policy, the user must meet one of the two requirements. I.e. they can be on an approved mobile app (as long as the iOS Authenticator or Android Company Portal apps are installed), or they can be on a managed and compliant device (or domain joined PC).  Here are some examples to help illustrate this:
* If a user is targeted by both a MAM CA policy and a device CA policy and tries to connect from the OneDrive app, they will be able to access company files on SharePoint online if one of the two following conditions are true:
  * OneDrive has been approved for MAM CA
  * The device that is used to access is compliant.  
* If a user tries to connect from the native iOS email app, she will be required to be on a managed and compliant device (since the native mail app cannot be approved).
* If a user tries to connect from a Windows home PC, the device CA policy will apply (i.e. she must be on a domain joined PC).
