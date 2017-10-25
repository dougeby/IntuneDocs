---
# required metadata

title: Get ready to configure app protection policies for Windows 10 
titlesuffix: "Azure portal"
description: "Setup mobile application management (MAM) provider in Azure AD"
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Get ready to configure app protection policies for Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Enable mobile application management (MAM) for Windows 10 by setting the MAM provider in Azure AD. Setting a MAM provider in Azure AD allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune. The enrollment state can be either MAM or mobile device management (MDM).

> [!NOTE]
> Devices with a MAM enrollment state are required to be Azure AD joined.

## To configure the MAM provider

1. Sign in to the Azure portal, and choose **Azure Active Directory.**

2. Choose **Mobility (MDM and MAM)** in the **Manage** group.

3. Click **Microsoft Intune**.

4. Configure the settings in the  **Restore default MAM URLs** group on the **Configure** blade.

    **MAM user scope**  
      Use MAM auto-enrollment to manage enterprise data on your employees' Windows devices. MAM auto-enrollment will be configured for bring your own device scenarios.

     - **None**  
     Select if all users can be enrolled in MAM.  
     - **Some**  
     Select Azure AD groups that contain users who will be enrolled in MAM.  
     - **All**  
     Select if all users can be enrolled in MAM.  

    **MAM terms of use URL**  
     The URL of the terms of use endpoint of the MAM service. The terms-of-use endpoint is used to display the terms of service to end-users before enrolling their devices for management. The terms-of-use text informs users about the policies enforced on the mobile device. 

    **MAM discovery URL**  
    The URL of the enrollment endpoint of the MAM service. The enrollment endpoint is used to enroll devices for management with the MAM service. 

    **MAM compliance URL**  
      The URL of the compliance endpoint of the MAM service. When a user is denied access to a resource from a non-compliant device, a link to the compliance URL is displayed to the user. Users can navigate to this URL hosted by the MAM service, in order to understand why their device is considered non-compliant. Users can also initiate self-service remediation so their device becomes compliant and they can continue to access resources. 

5.  Click **Save**.

## Next steps

[Create a WIP app protection policy](windows-information-protection-policy-create.md)
