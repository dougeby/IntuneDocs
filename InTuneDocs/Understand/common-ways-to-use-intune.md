---
title: Common ways to use Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: jeffgilb
---
# Common ways to use Intune

As the use of personal devices in the workplace expands, IT is challenged with managing a data environment where devices contain a mix of work-related and personal data. In addition, it must grant the right level of access per device, user, and user activity, and handle the use of multiple accounts and identities on a device. This article describes several common ways to use Microsoft Intune following the basic premise that the more IT control required, the more *as appropriate* access for employees.

>[!NOTE] Do you want to know how Microsoft IT uses Intune to enable Microsoft employees to access corporate resources on their mobile devices while also keeping corporate data protected? [Read this technical case study](https://www.microsoft.com/itshowcase/Article/Content/588) to see in detail how Microsoft IT uses Intune and other services to manage identity, devices, and apps, and data.  

## Unknown device
The following table describes common usage scenarios for IT management of unknown devices.

|Scenario feature|More information|
|---------------|----------------|
|Example|Kiosk at a hotel|
|Type of user|Information worker|
|What you can access|Employees can access corporate data only within a protected browser session|
|What you can't access|Employees can't download anything
|What's managed|Browswer session|
|Key features|Web conditional access, web session protection, and multi-factor authentication|

## Personal devices
The following table describes common usage scenarios for IT management of personal devices.

|Scenario feature|More information|
|---------------|----------------|
|Example|Personal iPad or home PC|
|Type of user|Information worker|
|What you can access|Employees can use mobile productivity apps controlled by IT to prevent company data leakage.|
|What you can't access|Employees can't access the corporate network, sync data, or use private apps.|
|What's managed|Managed productivity apps and a managed web browser.|
|Key features|Desktop and mobile application management conditional access, mobile application management without device enrollment, Azure Rights Management Service, Azure Remote App, and multi-factor authentication|

## Managed devices
The following table describes common usage scenarios for IT management of managed devices.

|Scenario feature|More information|
|---------------|----------------|
|Example|Company provided phone|
|Type of user|Information worker|
|What you can access|Employees can access all mobile apps, access the corporate network, and sync corporate documents.|
|What you can't access|Employees get full access per IT policies.|
|What's managed|All mobile devices, Windows PCs, and apps used by employees.|
|Key features|Desktop and mobile application management conditional access, mobile application management without device enrollment, mobile application management with device enrollment, Azure Rights Management Service, Azure Remote App, and multi-factor authentication.|

## Shared devices
The following table describes common usage scenarios for IT management of shared devices.

|Scenario feature|More information|
|---------------|----------------|
|Example|Mobile retail point of sale tablet|
|Type of user|Task worker|
|What you can access|Employees use the specific shared apps needed for their task.|
|What you can't access|Anything else.|
|What's managed|A locked down device with specific apps.|
|Key features|Windows 10 provision profile, DEP/Configurator, kiosk mode.|
