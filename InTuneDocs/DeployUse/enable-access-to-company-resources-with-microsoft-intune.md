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
[!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] Wi-Fi and VPN profiles work together to help your users gain access to the files and resources they need to do their work successfully, wherever they are.

## Resource access profiles and supported platforms

|Intune policy|What it does|Windows 8.1 and later|Windows Phone 8.1 and later|iOS|Android|Samsung KNOX|
|-----------------|----------------|-------------------------|-------------------------------|-------|-----------|----------------|
|[Wi-Fi profiles](wi-fi-profiles-in-microsoft-intune.md)|Deploy wireless network settings to your users. By deploying these settings, you minimize the end-user effort required to connect to the corporate network.|Yes (you can import a Windows Wi-Fi profile)|Yes (you can configure OMA-URI) <sup>1</sup>|Yes|Yes|Yes|
|[VPN profiles](vpn-profiles-in-microsoft.intune.md)|Deploy Virtual Private Network (VPN) settings to your users. By deploying these settings, you minimize the end-user effort required to connect to resources on the corporate network.|Yes|Yes|Yes|Yes|Yes|
|[Certificate profiles](certificates-in-microsoft-intune-for-securing-access-to-resources.md)|Help secure access to company resources including wireless networks and VPN connections.|Yes|Yes|Yes|Yes|Yes|
|[Email profiles](enable-access-to-company-resources-with-microsoft-intune.md)|Create, deploy and monitor native email client settings on devices in your organization.
.|No|Yes|Yes|No|Yes|
>NOTE
> See [this blog post](http://blogs.technet.com/b/microsoftintune/archive/2015/02/23/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1.aspx) for information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.
## See Also
[Configure and manage devices with Microsoft Intune](configure-and-manage-devices-with-microsoft-intune.md)
