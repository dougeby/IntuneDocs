---
# required metadata

title: Manage Intune licenses | Microsoft Intune
description: Explains how to assign licenses to users for your Intune subscription
keywords:
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage Intune licenses
Before users can sign in to use the Intune service or enroll their devices into management, you must first be assign each user a license to your Intune subscription by using the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854). Once assigned a license, users' names will appear in the Intune Administration console. Users can then enroll up to fifteen devices.

Organizations that use Microsoft's Enterprise Mobility Suite (EMS) might have users who only require Azure Active Directory Premium or Intune services in the EMS package. You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx). For more information, see [Manage Intune licenses using PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## How Intune licenses are assigned
When user accounts are synchronized from your on-premsies Active Directory or manually added to your cloud services subscription via the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854), they are not automatically assigned an Intune license. Instead, at a later time, an Intune tenant administrator must edit the user account to assign a license to the user from the Office 365 portal.

When your subscription shares Azure AD with other cloud services associated with your subscription, you also have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] until you assign a license to each of them.

> [!TIP]
> If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options.

## Assign an Intune user license

You use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.

1.  Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) using your tenant administrator credentials and then select **People** > **All Users**.

2.  Select the user account that you want to assign an Intune user license to, and then select either **Microsoft Intune** (standalone) or **Enterprise Mobility Suite**.

3.  The user account now has the needed permissions to use the service and enroll devices into management.

### Use PowerShell to selectively manage EMS user licenses
Organizations that use Microsoft's Enterprise Mobility Suite (EMS) might have users who only require Azure Active Directory Premium or Intune services in the EMS package. You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).

To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed. You can install PowerShell on a local computer or on an ADFS server.

You must create a new license SKU definition that applies only to the desired service plans. To do this, disable the plans you don’t want to apply. For example, you might create a license SKU definition that does not assign an Intune license. To see a list of available services, type:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

You can run the following command to exclude the Intune service plan. You can use the same method to expand to an entire security group or you can use more granular filters.

**Example 1**
Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Verify with:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Example 2**
Disable the Intune portion of EMS license for a user that is already assigned with a license:

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Verify with:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Next steps
Congratulations! You have just completed step 4 of the *Intune quick start guide*.
>[!div class="step-by-step"]

>[&larr; **Sync users to Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organize users and devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  
