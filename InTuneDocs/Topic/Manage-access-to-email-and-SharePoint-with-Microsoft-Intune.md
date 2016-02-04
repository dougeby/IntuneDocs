---
title: Manage access to email and SharePoint with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
author: karthikaraman
---
# Manage access to email and SharePoint with Microsoft Intune
Use **conditional access** in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] to help secure email and other services depending on conditions you specify.

Watch this four minute video to see an overview of how you can use this feature in your organization.

![](../Image/Intune_CondlAccess.PNG)

A typical flow for conditional access might look as follows:

![](../Image/ConditionalAccess4.png)

Use conditional access to manage access to Microsoft **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**, and **SharePoint Online**.

You can control access to Exchange Online and Exchange On-premises from the following mail apps:

-   The built-in app for Android 4.0 and later, Samsung Knox 4.0 Standard and later

-   The built-in app for iOS 7.1 and later

-   The built-in app for Windows Phone 8.1 and later

-   The mail application on Windows 8.1 and later

-   The Microsoft Outlook app for Android and iOS (for Exchange Online only)

You can control access to SharePoint Online from the following apps for the listed platforms:

-   Microsoft Office Mobile (Android)

-   Microsoft OneDrive (Android and iOS)

-   Microsoft Word (iOS)

-   Microsoft Excel (iOS)

-   Microsoft PowerPoint (iOS)

-   Microsoft OneNote (iOS)

Office desktop applications can access Exchange Online and SharePoint Online on PCs running:

-   Office desktop 2013 and later with [modern authentication](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/) enabled.

-   Windows 7.0 or Windows 8.1

> [!NOTE]
> PCs should be domain joined or be complaint with the policies set in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

To implement conditional access, you configure two policy types in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]:

-   **Compliance policies** are optional policies you can deploy to users and devices and evaluate settings like:

    -   Passcode

    -   Encryption

    -   Whether the device is jailbroken or rooted

    -   Whether email on the device is managed by an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy

    If no compliance policy is deployed to a device, then any applicable conditional access policies will treat the device as compliant.

-   **Conditional access policies** are configured for a particular service, and define rules such as which Azure Active Directory security user groups or [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups will be targeted and how devices that cannot enroll with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will be managed.

    Unlike other [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies, you do not deploy conditional access policies. Instead, you configure these once, and they apply to all targeted users.

When devices do not meet the conditions you configure, the user is guided though the process of enrolling the device and fixing the issue that prevents the device from being compliant.

## Getting started with conditional access
Before you start using conditional access, ensure that you have the correct requirements in place:

> [!IMPORTANT]
> Conditional access does not work with devices enrolled with [device enrollment manager](https://technet.microsoft.com/en-us/library/dn764961.aspx) since the device is not linked to a user in Azure Active Directory.

-   [Exchange Online (using the shared multi-tenant environment)](#Exo)

-   [Exchange Online Dedicated](#ExoDedicated)

-   [Exchange On-premises](#ExOnPrem)

-   [SharePoint Online](#Spo)

-   [Conditional Access for PCs](#PC)

### <a name="Exo"></a>Exchange Online (using the shared multi-tenant environment)
Conditional access to Exchange Online supports devices that run:

-   Windows 8.1 and later (when enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)])

-   Windows 7.0 or Windows 8.1 (when domain joined)

-   Windows Phone 8.1 and later

-   iOS 7.1 and later

-   Android 4.0 and later, Samsung Knox Standard 4.0 and later

Additionally:

-   Devices must be registered with the Azure Active Directory Device Registration Service (AAD DRS).

    Domain joined PCs must be automatically registered with Azure Active Directory through group policy or MSI. The [Conditional Access for PCs](#PC) section in this topic describes all the requirements for enabling conditional access for a PC.

    AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

-   You must use an Office 365 subscription that includes Exchange Online (such as E3) and users must be licensed for Exchange Online.

-   The optional **Microsoft Intune service to service connector** connects [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to Microsoft Exchange Online and helps you manage device information through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

    If you configure the connector, some Exchange ActiveSync policies from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] might be visible in the Office console but are not set as default policies and do not affect devices.

    > [!NOTE]
    > Do not configure the service to service connector if you intend to use conditional access for both Exchange Online and Exchange On-premises

### <a name="ExoDedicated"></a>Exchange Online Dedicated
Conditional access to Exchange Online Dedicated supports devices that run:

-   Windows 8 and later (when enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)])

-   Windows 7.0 or Windows 8.1 (when domain joined)

    Conditional access to domain joined PCs only to tenants in the new Exchange Online dedicated environment.

-   Windows Phone 8 and later

-   Any iOS device that uses an Exchange ActiveSync (EAS) email client

-   Android 4 and later.

-   For tenants in the legacy Exchange Online Dedicated environment:

    You must use the **on-premises Exchange connector** which connects [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to Microsoft Exchange On-premises. This lets you manage devices through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)).

-   For tenants in the new Exchange Online Dedicated environment:

    The optional **Microsoft Intune service to service connector** connects [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to Microsoft Exchange Online and helps you manage device information through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

> [!IMPORTANT]
> Ensure that you are using the latest version of the **on-premises Exchange connector**.

### <a name="ExOnPrem"></a>Exchange On-premises
Conditional access to Exchange On-premises supports:

-   Windows 8 and later (when enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)])

-   Windows Phone 8 and later

-   Native email app on iOS.

-   Native email app on Android 4 or later

-   Microsoft Outlook app on Android and iOS is not supported.

Additionally:

-   Your Exchange version must be Exchange 2010 or later. Exchange server Client Access Server (CAS) array is supported.

    > [!TIP]
    > If your Exchange environment is in a CAS server configuration, then you must configure the on-premises Exchange connector to point to one of the CAS servers.

-   You must use the **on-premises Exchange connector** which connects [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to Microsoft Exchange On-premises. This lets you manage devices through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)).

    -   Make sure that you are using the latest version of the **on-premises Exchange connector**. The on-premise Exchange connector available to you in the Intune console is specific to your Intune tenant and cannot be used with any other tenant. You should also ensure that the exchange connector for your tenant is installed on exactly one machine and not on multiple machines.

        This connector should be downloaded from the Intune admin console.  For a walkthrough on how to configure the on-premises Exchange connector, see [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_EX_OP).

    -   The connector can be installed on any machine as long as that machine is able to communicate with the Exchange server.

    -   The connector indeed supports Exchange CAS environment. You can technically install the connector on the Exchange CAS server directly if you wish to, but it is not recommended as it will increase the load on the server. 
        When configuring the connector, you must set it up to talk to one of the Exchange CAS servers.

-   Exchange ActiveSync can be configured with certificate based authentication, or user credential entry

### <a name="Spo"></a>SharePoint Online
Conditional access to SharePoint Online supports devices that run:

-   Windows 8.1 and later (when enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)])

-   Windows 7.0 or Windows 8.1 (when domain joined)

-   Windows Phone 8.1 and later

-   iOS 7.1 and later

-   Android 4.0 and later, Samsung Knox Standard 4.0 or later

Additionally:

-   Devices must be registered with the Azure Active Directory Device Registration Service (AAD DRS).

    AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

    Domain joined PCs must be automatically registered with Azure Active Directory through group policy or MSI. The [Conditional Access for PCs](#PC) section in this topic describes all the requirements for enabling conditional access for a PC.

-   A SharePoint Online subscription is required and users must be licensed for SharePoint Online.

## <a name="PC"></a>Conditional Access for PCs
You can setup conditional access for PCs that run Office desktop applications to access **Exchange Online** and **SharePoint Online** for PCs that meet the following requirements:

-   The PC must be running Windows 7.0 or Windows 8.1.

-   The PC must either be domain joined or compliant.

    In order to be compliant, the PC must be enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and comply with the policies.

    For domain joined PCs, you must  set it up to [automatically register the device](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.

-   [Office 365 modern authentication must be enabled](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/), and have all the latest Office updates.

    Modern authentication brings Active Directory Authentication Library (ADAL) based sign-in to Office 2013 Windows clients and enables better security like **multi-factor authentication**, and **certificate-based authentication**.

-   Setup ADFS claims rules to block non-modern authentication protocols. Step by step instructions are detailed in scenario 3 - [block all access to O365 except browser based applications](https://technet.microsoft.com/en-us/library/dn592182.aspx).

## Next Steps
Read the following topics to learn how to configure compliance policies and conditional access policies for your required scenario:

-   [Manage device compliance policies for Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md)

-   [Manage email access with Microsoft Intune](../Topic/Manage-email-access-with-Microsoft-Intune.md)

-   [Manage SharePoint Online access with Microsoft Intune](../Topic/Manage-SharePoint-Online-access-with-Microsoft-Intune.md)

## See Also
[Protect data and devices with Microsoft Intune](../Topic/Protect-data-and-devices-with-Microsoft-Intune.md)

