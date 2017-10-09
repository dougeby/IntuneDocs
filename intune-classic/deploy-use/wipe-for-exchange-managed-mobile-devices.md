---
# required metadata

title: Wipe for Exchange managed mobile devices 
description: Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: lancecra
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector. The following table describes the wipe capabilities available through Exchange ActiveSync:

|Type of wipe|Windows 8.1 and Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Full wipe|Removes mail account and cached mail.|XFactory reset.|Factory reset.|
|Selective wipe/email|Removes email account.|Not supported.|Not supported.|
|Selective wipe/policies|Policy enforcement removed, but settings are not changed|XPolicy enforcement removed, but settings are not changed.|Policy enforcement removed, but settings are not changed.|
