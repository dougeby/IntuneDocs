---
# required metadata

title: Remove SCEP or PKCS certificates in Microsoft Intune - Azure | Microsoft Docs
titleSuffix:
description: Administrators can use the wipe or retire action to remove certificates from Microsoft Intune. There are some scenarios where the certificates are automatically removed, such as unenrolling a device or removing a compliance policy. There are some scenarios where certificates automatically remain on the device, such as when the Intune license is lost or removed. See the different ways for Android, Android Enterprise, iOS, macOS, and Windows devices.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Remove SCEP and PKCS certificates in Microsoft Intune

In Microsoft Intune, you can add SCEP and PKCS certificates to devices. These certificates can also be removed when you [wipe](devices-wipe.md#wipe) or [retire](devices-wipe.md#retire) the device. There are some other scenarios where certificates are automatically removed, and some scenarios where certificates stay on the device.

This article lists some common scenarios, and the impact on PKCS and SCEP certificates.

> [!NOTE]
> To remove and revoke certificates for a user that's being removed from Active Directory (AD) or Azure AD, be sure to follow the steps in order:
>
>    1. Wipe or retire the user's device
>    2. Remove the user from AD or Azure AD

## Windows devices

#### SCEP certificates

- A SCEP certificate is revoked *and* removed when:

  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action
  - Device is removed from Azure Active Directory (AD) group
  - Certificate profile is removed from the group assignment

- A SCEP certificate is revoked when:
  - Administrator changes or updates the SCEP profile

- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- SCEP certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD

#### PKCS certificates

- A PKCS certificate is revoked *and* removed when:

  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- PKCS certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD
  - Administrator changes or updates the PKCS profile
  - Certificate profile is removed from the group assignment


## iOS devices

#### SCEP certificates

- A SCEP certificate is revoked *and* removed when:

  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action
  - Device is removed from Azure Active Directory (AD) group
  - Certificate profile is removed from the group assignment

- A SCEP certificate is revoked when:
  - Administrator changes or updates the SCEP profile

- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- SCEP certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD

#### PKCS certificates

- A PKCS certificate is revoked *and* removed when:

  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- A PKCS certificate is removed when:
  - Certificate profile is removed from the group assignment
  
- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- PKCS certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD
  - Administrator changes or updates the PKCS profile

## Android KNOX devices

#### SCEP certificates

- A SCEP certificate is revoked *and* removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action

- A SCEP certificate is revoked when:
  - Administrator runs [retire](devices-wipe.md#retire) action
  - Device is removed from Azure Active Directory (AD) group
  - Certificate profile is removed from the group assignment
  - Administrator removes the user or group from Azure Active Directory (AD)
  - Administrator changes or updates the SCEP profile

- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- SCEP certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD

#### PKCS certificates

- A PKCS certificate is revoked *and* removed when:

  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- Root certificate is removed when:
  - An end user unenrolls
  - Administrator runs [wipe](devices-wipe.md#wipe) action
  - Administrator runs [retire](devices-wipe.md#retire) action

- PKCS certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD
  - Administrator changes or updates the PKCS profile
  - Certificate profile is removed from the group assignment
  
  
> [!NOTE]
> Android for work devices are not validated for the above scenarios. 
> Android legacy devices (any non-Samsung, non-work profile device) are not enabled for certificate removal. 

## macOS certificates

#### SCEP certificates

- A SCEP certificate is revoked *and* removed when:
  - An end user unenrolls
  - Administrator runs [retire](devices-wipe.md#retire) action
  - Device is removed from Azure Active Directory (AD) group
  - Certificate profile is removed from the group assignment

- A SCEP certificate is revoked when:
  - Administrator changes or updates the SCEP profile

- SCEP certificates **stay** on the device (certificates aren't revoked nor removed) when:
  - An end user loses the Intune license
  - Administrator withdraws the Intune license
  - Administrator removes the user or group from Azure AD

> [!NOTE]
> Using the [wipe](devices-wipe.md#wipe) action to factory reset macOS devices is not supported.

#### PKCS certificates

PKCS certificates are not supported on macOS.

