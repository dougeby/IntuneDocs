---
title: Protect Windows devices with multi-factor authentication
ms.custom: na
ms.prod: configuration-manager
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
author: Nbigman
---
# Protect Windows devices with multi-factor authentication
Microsoft Intune integrates multi-factor authentication (MFA) to help you secure your corporate resources. MFA requires authentication factors such as text authentication in addition to usernames and passwords. Intune supports the use of MFA during enrollment of Windows 8.1 or later, Windows Phone 8.1, or Windows 10 Desktop and Mobile devices. 

## On-premises infrastructure requirements for ADFS MFA
To set up multi-factor authentication, you need:

-   **An Active Directory domain to which the ADFS server is joined.**

-   **Active Directory Federation Services (ADFS) server, configured for MFA.** A server running Windows Server 2012 R2, set up as an ADFS server. For more information, see: [Secure cloud and on-premises resources using Azure Multi-Factor Authentication Server with Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

All of the servers listed above must meet the system requirements provided in [System Requirements and Installation Information for Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

#### MFA with Intune
If your organization has on-premises IT infrastructure that includes an Active Directory domain with Active Directory Federation Services (ADFS), you can configure MFA on your federation server and then enable MFA for Intune enrollment. By configuring MFA on Intune, you enable users to authenticate once, during enrollment, then be able to access corporate resources without repeating the MFA process each time.

>[!NOTE]
>MFA can be required on a per-user or per-group basis on the ADFS server.  

#### MFA without Intune
If you configure MFA on your federation server but you don’t enable MFA for enrollment in Intune, users will need to use MFA each time that they access corporate resources (not just at device enrollment).

You can also use Azure Active Directory (AAD) MFA to require MFA each time that users access corporate resources, on a per-user basis. AAD MFA is a cloud service that does not require any on-premises IT infrastructure. To learn how to set up AAD MFA, see [Getting started with Azure Multi-Factor Authentication in the cloud.](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Requiring ADFS MFA during enrollment of Windows devices
For information about how to enable MFA in ADFS, see [Manage Risk with Additional Multi-Factor Authentication for Sensitive Applications](http://technet.microsoft.com/library/dn280949.aspx).

## Set up device enrollment MFA in Intune
>[!Important]  
>Enable MFA in your Azure AD tenant or on-premises environment before you require MFA for Intune enrollment of Windows devices. If you do not, users will receive an error message when they try to enroll their Windows devices, or when they attempt to Azure AD join their devices, if automatic enrollment during Azure AD Join is configured.

1.  In the Intune admin console, click **Admin** &gt; **Mobile Device Management** &gt; **Multi-factor authentication**.

2.  Click **Configure Multi-factor Authentication**, and then click **Enable Multi-factor Authentication**.

