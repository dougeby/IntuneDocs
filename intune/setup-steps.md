---
# required metadata

title: Set up Intune
description: Requirements and prerequisites for starting to use your Intune subscription
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/15/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Set up Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

These set-up steps help you enable mobile device management. Before you give users access company resources on devices or manage device settings, those devices should be brought into management. Device management lets you configure devices and set conditions for access. These can improve user experience and help protect your data.

If you're currently using Microsoft System Center Configuration Manager to manage computers and servers, you can [extend Configuration Manager to manage mobile devices](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

>[!TIP]
>If you purchase at least 150 licenses for Intune in an eligible plan, you can use the *FastTrack Center Benefit*. With this service, Microsoft specialists work with you to get your environment ready for Intune. See [FastTrack Center Benefit for Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).

Some steps such as configuring a custom domain and adding apps or configuring devices are optional, depending upon your company's needs. Other steps, such as adding users and setting the MDM authority are required for most management scenarios that involve device management.

| Steps | Status  |
| ------------- |-------------|
| 1  | [Prerequisites](supported-devices-browsers.md) - Need-to-know info before you start|
| 2 |  [Sign in to Intune](account-sign-up.md) - Sign in to your trial subscription or create a new subscription |  
| 3 | [Configure domain name](custom-domain-name-configure.md) - Set DNS registration to connect your company's domain name with Intune  |
| 4 | [Add users](users-add.md) - Manually add users or connect Active Directory to synchronize users with Intune  |
| 5 | [Assign licenses](licenses-assign.md) - Give users permission to use Intune|
| 6 |  [Add groups](groups-add.md) - Use user and device groups to simplify management tasks |
| 7 | [Add apps](apps-add.md) - Enable settings and apps that can be deployed to users |
| 8 | [Configure devices](device-profiles.md) - Set up profiles that manage devices and access to company resources |
| 9 | [Customize Company Portal](company-portal-app.md) - Customize the Intune Company Portal   |
| 10 | [Enable device enrollment](mdm-authority-set.md) - Enable Intune management of iOS, Windows, Android, and Mac devices |
