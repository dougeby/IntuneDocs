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

Before diving into implementation it is important to gain clarity on your company’s enterprise mobility business goals and the scenarios that will best support those goals. Below are short introductions to the 6 most common scenarios that rely on Intune, accompanied with links to more information on how to plan and deploy each of them. This is not intended to be a complete set of scenarios or implementation approaches.

>[!NOTE] Do you want to know how Microsoft IT uses Intune to enable Microsoft employees to access corporate resources on their mobile devices while also keeping corporate data protected? [Read this technical case study](https://www.microsoft.com/itshowcase/Article/Content/588) to see in detail how Microsoft IT uses Intune and other services to manage identity, devices, and apps, and data.  

## Securing your on-premises email and data so it can be safely accessed by mobile devices
Most enterprise mobility strategies begin with a plan to enable secure access to email for mobile devices out on the internet. Many organizations still have some corporate data and application servers, like Microsoft Exchange, hosted behind a firewall on their corporate network. Intune and the enterprise mobility suite provide a uniquely integrated conditional access solution that ensures no devices or apps will be able to access Exchange email unless they meet your company’s compliance requirements (enrolled with Intune, supported OS version, device pin, etc.), all without deploying a new machine to your DMZ! Such a solution for email can be extended to other mobile apps that require secure access to data behind a corporate firewall.

Learn more about how to plan and deploy Intune to help secure on-premises email and data.

## Securing your Office 365 email and data so it can be safely accessed by mobile devices
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies, purus lectus malesuada libero, sit amet commodo magna eros quis urna. Nunc viverra imperdiet enim.
Fusce est. Vivamus a tellus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Proin pharetra nonummy pede.
Mauris et orci. Aenean nec lorem. In porttitor. Donec laoreet nonummy augue.

Learn more about how to plan and deploy Intune to help secure Office 365 email and data.

## Offer a “bring your own device” (BYOD) program to all employees
BYOD continues to grow in popularity among organizations as a means to reduce hardware expenditures and increase user choice. Just about everyone has a personal phone these days so why put another one in their pocket? The main challenge has always been to convince employees to enroll their personal device into management, as they are fearful of what their IT department will be able to see and do with their device. Intune offers users a choice: if you just want to access Office 365 email and files you don’t need to enroll the device but must use the Office apps (with data loss prevention policies applied), however, if you want to access other corporate resources (VPN, WiFi, etc.) then you must enroll.  Either way the corporate data will be secured by policies defined by the IT department.

Learn more about how to plan and deploy Intune to support BYOD.

## Issue corporate owned phones to your information workers
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies, purus lectus malesuada libero, sit amet commodo magna eros quis urna.
Nunc viverra imperdiet enim. Fusce est. Vivamus a tellus.
Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Proin pharetra nonummy pede. Mauris et orci.
Aenean nec lorem. In porttitor. Donec laoreet nonummy augue.

Learn more about how to plan and deploy Intune to support corporate owned devices.

## Issue limited-use shared tablets to your task workers
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies, purus lectus malesuada libero, sit amet commodo magna eros quis urna.
Nunc viverra imperdiet enim. Fusce est. Vivamus a tellus.
Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Proin pharetra nonummy pede. Mauris et orci.
Aenean nec lorem. In porttitor. Donec laoreet nonummy augue.

Learn more about how to plan and deploy Intune to support shared tablets.

## Enable your employees to securely access Office 365 from an unmanaged public kiosk
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies, purus lectus malesuada libero, sit amet commodo magna eros quis urna. Nunc viverra imperdiet enim. Fusce est.
Vivamus a tellus. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Proin pharetra nonummy pede. Mauris et orci. Aenean nec lorem.
In porttitor. Donec laoreet nonummy augue. Suspendisse dui purus, scelerisque at, vulputate vitae, pretium mattis, nunc. Mauris eget neque at sem venenatis eleifend. Ut nonummy.

Learn more about how to plan and deploy Intune to support kiosks.


<!--
As the use of personal devices in the workplace expands, IT is challenged with managing a data environment where devices contain a mix of work-related and personal data. In addition, it must grant the right level of access per device, user, and user activity, and handle the use of multiple accounts and identities on a device. This article describes several common ways to use Microsoft Intune following the basic premise that the more IT control required, the more *as appropriate* access for employees.

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
-->
