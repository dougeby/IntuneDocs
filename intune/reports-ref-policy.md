---
# required metadata
title: Policy | Microsoft Docs
description: Reference topic for the Policy category of entity collections in the Intune Data Warehouse API.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Policy

The **Policy** category contains entities for mobile devices that track information such as:

  -  Inventory of device configuration profiles, app configuration profiles, and compliance policies  
  -  Number of devices in the succeeded, pending, failed, or error state per day  
  -  Number of users in the succeeded, pending, failed, or error state per day  
  -  Cumulative number of devices in the succeeded, pending, failed, or error state  

## Policy

The **Policy** entity lists device configuration profiles, app configuration profiles, and compliance policies. You can assign the policies with Mobile Device Management (MDM) to a group in your enterprise.

| Property  | Description | Example |
|---------|------------|--------|
| PolicyKey |Unique Key to represent the policy in the data warehouse |123 |
| PolicyId |Unique identifier of the Policy in the data warehouse |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Name of the Policy |"Windows 10 Baseline" |
| PolicyVersion |Version of the Policy. When the policy is edited or changed, a newer version is created. |1, 2, 3 |
| IsDeleted |Indicates whether the Policy record has been updated.  True- policy has a new record with updated fields. False- the latest record for the policy. |True/False |
| StartDateInclusiveUTC |Date and time in UTC when the policy was created in the data warehouse |11/23/2016 12:00:00 AM |
| DeletedDateUTC |Date and time in UTC when IsDeleted changed to True |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Date and time in UTC when the policy was last modified in the data warehouse |11/23/2016 12:00:00 AM |

## PolicyType

The **PolicyType** entity lists types of device configuration profiles, app configuration profiles, and Compliance policies. You can assign the policies with Mobile Device Management (MDM) to a group in your enterprise.

| Property  | Description | Example |
|---------|------------|--------|
| PolicyTypeId |Unique identifier of the policy in the source system |123 |
| PolicyTypeKey |Unique identifier of the policy in the data warehouse |1 |
| PolicyTypeName |Name of the policy type. |Windows 10 Compliance policy |

## DeviceConfigurationProfileDeviceActivity

The **DeviceConfigurationProfileDeviceActivity** entity lists the number of devices in the succeeded, pending, failed, or error state per day. The number reflects the Device configuration profiles assigned to the entity. For example, if a device is in the succeeded state for all its assigned policies, it increments the succeeded counter up one for that day. If a device has two profiles assigned to it, one in the succeeded state and another in an error state, the entity increments the Succeeded counter and place the device in the error state. The entity lists how many devices are in which state on a given day over the last 30 days.

| Property  | Description | Example |
|---------|------------|--------|
| DateKey |Date Key when the Device Configuration Profile check-in was recorded in the data warehouse |20160703 |
| Pending |Number of unique Devices in pending state |123 |
| Succeeded |Number of unique Devices in success state |12 |
| Error |Number of unique Devices in error state |10 |
| Failed |Number of unique Devices in failed state |2 |

## UserConfigurationProfileDeviceActivity

The **UserConfigurationProfileDeviceActivity** entity lists the number of users in the succeeded, pending, failed, or error state per day. The number reflects the Device configuration profiles assigned to the entity. For example, if a user is in the succeeded state for all their assigned policies, it moves up the succeeded counter by one for that day. If a user has two profiles assigned to them, one in the succeeded state while the other is in an error state, we count the user in the error state.  The **UserConfigurationProfileDeviceActivity** entity lists how many users are in which state on a given day over the last 30 days.

| Property  | Description | Example |
|---------|------------|--------|
| DateKey |Date Key when the Device Configuration Profile check-in was recorded in the data warehouse |20160703 |
| Pending |Number of unique Users in pending state |123 |
| Succeeded |Number of unique Users in success state |12 |
| Error |Number of unique Users in error state |10 |
| Failed |Number of unique Users in failed state |2 |

## PolicyTypeActivity

The **PolicyTypeActivity** entity lists the cumulative number of devices in the succeeded, pending, failed, or error state. It lists these states with respect to a device configuration profile, app configuration profile, or compliance policy per day.

| Property  | Description | Example |
|---------|------------|--------|
| DateKey |Date Key when the device Configuration profile check-in was recorded in the data warehouse |20160703 |
| PolicyKey |Policy Key, can be joined with Policy to get the policyName |Windows 10 baseline |
| PolicyTypeKey |Type of Policy Key,  can be joined with Policy Type to get the policy type name |Windows10Compliance Policy |
| Pending |Number of unique devices in pending state |123 |
| Succeeded |Number of unique devices in success state |12 |
| Error |Number of unique devices in error state |10 |
| Fail- |Number of unique devices in failed state |2 |