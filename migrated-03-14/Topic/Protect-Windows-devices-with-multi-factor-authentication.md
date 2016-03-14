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
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] integrates multi-factor authentication (MFA) to allow you to better secure your corporate resources by requiring additional verification from users beyond their usernames and passwords (for example, using a phone call or text message). [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] supports the use of MFA during enrollment of Windows 8.1 or later, Windows Phone 8.1, or Windows 10 Desktop and Mobile devices (and the MFA requirement can be assigned on a per-user or per-group basis on the ADFS server). If your organization has on-premises IT infrastructure that includes an Active Directory domain with Active Directory Federation Services (ADFS) configured, you can configure MFA on your federation server and then enable MFA for enrollment in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. If you configure MFA on your federation server, but you don’t enable MFA for enrollment in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], users will need to use MFA each time that they access corporate resources.

> [!IMPORTANT]
> The MFA feature will be enabled in Configuration Manager at the next Intune service update.

You can also use Azure Active Directory (AAD) MFA to require MFA each time that users access corporate resources, and this requirement can be enabled on a per-user basis. AAD MFA is a cloud service that does not require any on-premises IT infrastructure. To learn how to set up AAD MFA, see [Adding Multi-Factor Authentication to Azure Active Directory.](http://technet.microsoft.com/library/dn249466.aspx)

## <a name="Reqs_MFA"></a>On-premises infrastructure requirements for ADFS MFA
To set up multi-factor authentication, you need:

-   **An Active Directory domain to which the ADFS server is joined.**

-   **Active Directory Federation Services (ADFS) server, configured for MFA.** A server running Windows Server 2012 R2, set up as an ADFS server. For more information, see: [Using Multi-Factor Authentication with Windows Server 2012 R2 AD FS](http://msdn.microsoft.com/library/azure/dn807157.aspx)

All of the servers listed above must meet the system requirements provided in [System Requirements and Installation Information for Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

## Requiring ADFS MFA during enrollment of Windows devices
For information about how to enable MFA in ADFS, see [Manage Risk with Additional Multi-Factor Authentication for Sensitive Applications](http://technet.microsoft.com/library/dn280949.aspx).

#### To require enrollment MFA in the Intune Admin Console

1.  In the Intune administration console, click **Admin** &gt; **Mobile Device Management** &gt; **Multi-factor authentication**.

2.  Enable MFA in your Azure AD tenant or on-premises environment before you require MFA for Intune enrollment of Windows devices. If you do not, users will receive an error message when they try to enroll their Windows devices.

    > [!IMPORTANT]
    > If you do not first enable MFA in your Azure AD tenant before requiring it for Intune enrollment, and automatic MDM enrollment during Azure AD Join is configured, users will receive an error message when they attempt to Azure AD join their Windows devices.

3.  Click **Configure Multi-factor Authentication**, and then click **Enable Multi-factor Authentication**.

## See Also
[Protect data and devices with Microsoft Intune](../Topic/Protect-data-and-devices-with-Microsoft-Intune.md)

