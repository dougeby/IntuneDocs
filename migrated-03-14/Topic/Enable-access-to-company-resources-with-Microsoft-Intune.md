---
title: Enable access to company resources with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
author: Nbigman
---
# Enable access to company resources with Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**resource access profiles** work together to help your users gain access to the files and resources they need to do their work successfully, wherever they are.

[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] provides the following mobile device policies that help you to accomplish this goal. Click any item in the table for detailed information about how to configure the policy:

## Resource access profiles and supported platforms

|Intune policy|What it does|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|-----------------|----------------|-------------------------|-------------------------------|-------|-----------|----------------|
|[Certificate Profiles](https://technet.microsoft.com/library/dn818904.aspx)|Help secure access to company resources including wireless networks and VPN connections.|Yes|Yes|Yes|Yes|Yes|
|[Wi-Fi Profiles](https://technet.microsoft.com/library/dn818903.aspx)|Deploy wireless network settings to your users. By deploying these settings, you minimize the end-user effort required to connect to the corporate network.|Yes (you can import a Windows Wi-Fi profile)|Yes (you can configure OMA-URI) <sup>1</sup>|Yes|Yes|Yes|
|[VPN Profiles](https://technet.microsoft.com/library/dn818905.aspx)|Deploy Virtual Private Network (VPN) settings to your users. By deploying these settings, you minimize the end-user effort required to connect to resources on the corporate network.|Yes|Yes|Yes|Yes|Yes|
|[Email Profiles](https://technet.microsoft.com/library/dn800672.aspx)|Create, deploy and monitor Exchange ActiveSync email settings on devices in your organization.|No|Yes|Yes|No|Yes|
<sup>1</sup> See [this blog post](http://blogs.technet.com/b/microsoftintune/archive/2015/02/23/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1.aspx) for information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.

## See Also
[Configure and manage devices with Microsoft Intune](../Topic/Configure-and-manage-devices-with-Microsoft-Intune.md)

