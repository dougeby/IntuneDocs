---
# required metadata

title: Enable access to company resources with Microsoft Intune | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enable access to company resources with Microsoft Intune
Microsoft Intune Wi-Fi, VPN, and email profiles work together to help your users gain access to the files and resources they need to do their work successfully, wherever they are. Certificate profiles help secure that access.

## [Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md) and supported platforms

Deploy wireless network settings to your users. By deploying these settings, you minimize the end-user effort required to connect to the corporate network.
#### Supported platforms

|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Yes (you can import a Windows Wi-Fi profile)|Yes (you can configure OMA-URI) |Yes|Yes|Yes|

## [VPN profiles](vpn-connections-in-microsoft-intune.md) and supported platforms
Deploy Virtual Private Network (VPN) settings to your users. By deploying these settings, you minimize the end-user effort required to connect to resources on the corporate network.

|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Yes|Yes|Yes|Yes|Yes|

## [Email profiles](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) and supported platforms
Create, deploy and monitor native email client settings on devices in your organization.

|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|No|Yes|Yes|No|Yes|
> [!NOTE]
> [This Intune team blog post](http://blogs.technet.com/b/microsoftintune/archive/2015/02/23/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1.aspx) gives information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.

## [Certificate profiles](secure-resource-access-with-certificate-profiles.md) and supported platforms
Help secure access to company resources including wireless networks and VPN connections.

|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Yes|Yes|Yes|Yes|Yes|
