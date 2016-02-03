---
title: Upgrade Windows devices to the latest version with the edition upgrade policy in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
author: robstackmsft
---
# Upgrade Windows devices to the latest version with the edition upgrade policy in Microsoft Intune
The [!INCLUDE[wit_firstref](/Token/wit_firstref.xml)] **Edition Upgrade Policy** lets you automatically upgrade devices that run one of the following Windows 10 versions to a newer edition:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

## Before you start
Before you begin to upgrade devices to the latest version, you will need one of the following:
* A product key which is valid to install the new version of Windows on all devices you target with the policy
* A licence file from Microsoft which contains the licensing information to install the new version of Windows on all devices you target with the policy.

## Configure the edition upgrade policy

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy**.
2. In the Policy workspace, click **Configuration Policies** > **Add**.
3. In the **Create a New Policy** dialog box, expand **Windows**, and then click one of the following policies:
* **Edition Upgrade Policy (Windows 10 Desktop and later)**
* **Edition Upgrade Policy (Windows 10 Holographic and later)**
* **Edition Upgrade Policy (Windows 10 Mobile and later)**
4. Click **Create Policy**.
>**Note**
> You cannot create a configuration policy using recommended settings. You must create a custom policy. 
5. On the **Create Policy** page, specify the following options which are common to all of the edition upgrade policies.
* **Name** - Enter a name for the edition upgrade policy.
* **Description** - Optionally, enter a description for the policy that helps you identify it in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console.
* **Edition to upgrade to** - From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Hologrpahic, or Windows 10 Mobile that you want to upgrade targeted devices to.
* **Product Key** - Specify the product key that you obtained from Microsoft which can be used to upgrade all targeted devices.
* **License File** - Click **Browse** to select the license file you obtained from Microsoft that contains license information for the Winows edition you want to upgrade targeted devices to.
6. Click **Save Policy** once you are done.

## Deploy the edition upgrade policy

1. Deploy the edition upgrade policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).
A status summary and alerts In the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## See also
[Use policies to manage computers and mobile devices with Microsoft Intune](Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md)