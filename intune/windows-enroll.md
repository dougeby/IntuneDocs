---
# required metadata

title: Enroll Windows devices
titlesuffix: "Azure portal"
description: Enable Intune mobile device management (MDM) for Windows devices.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll Windows devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic helps IT administrators simplify Windows enrollment for their users. Once you've [set up Intune](setup-steps.md), users enroll Windows devices by [signing in](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) with their work or school account.  

As an Intune admin, you can simplify enrollment in the following ways:
- [Enable automatic enrollment](#enable-windows-10-automatic-enrollment) (Azure AD Premium required)
- [CNAME registration](#simplify-windows-enrollment-without-azure-ad-premium)
- [Enable bulk enrollment](windows-bulk-enroll.md) (Azure AD Premium and Windows Configuration Designer required)
- [Add a custom message](windows-enrollment-status.md) to greet your users when they enroll and view the progress of policy settings as they're applied

Two factors determine how you can simplify Windows device enrollment:

- **Do you use Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is included with Enterprise Mobility + Security and other licensing plans.
- **What versions of Windows clients will users enroll?** <br>Windows 10 devices can automatically enroll by adding a work or school account. Earlier versions must enroll using the Company Portal app.

||**Azure AD Premium**|**Other AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatic enrollment](#enable-windows-10-automatic-enrollment) |[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|
|**Earlier Windows versions**|[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|[User enrollment](#enable-windows-enrollment-without-azure-ad-premium)|

Organizations that can use automatic enrollment can also configure [bulk enroll devices](windows-bulk-enroll.md) by using the Windows Configuration Designer app.

**Multi-user support**<br>
Devices that run the Windows 10 Creators Update, and are Azure Active Directory domain-joined, are now supported for multi-user management by Intune. When standard users log on with their Azure AD credentials, they receive apps and policies assigned to their user name. Users cannot currently use the Company Portal for self-service scenarios like installing apps.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## Simplify Windows enrollment without Azure AD Premium
You can simplify enrollment for your users by creating a domain name server (DNS) alias (CNAME record type) that automatically redirects enrollment requests to Intune servers. If you don't create a DNS CNAME resource record, users attempting to connect to Intune must enter the Intune server name during enrollment.

**Step 1: Create CNAME** (optional)<br>
Create CNAME DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com.

Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users. If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, enrollment.manage.microsoft.com.

|Type|Host name|Points to|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hour|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hour|

If you have more than one UPN suffix, you need to create one CNAME for each domain name and point each one to EnterpriseEnrollment-s.manage.microsoft.com. If users at Contoso use name@contoso.com, but also use name@us.contoso.com, and name@eu.constoso.com as their email/UPN, the Contoso DNS admin should create the following CNAMEs:

|Type|Host name|Points to|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hour|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hour|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hour|

`EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

**Step 2: Verify CNAME** (optional)<br>
In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**. On the Intune blade, choose **Enroll devices** > **Windows Enrollment**. Enter the company website URL in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

## Tell users how to enroll Windows devices
Tell your users how to enroll their Windows devices and what to expect after they're brought into management.

> [!NOTE]
> End users must access the Company Portal website through Microsoft Edge to view Windows apps that you've assigned for specific versions of Windows. Other browsers, including Google Chrome, Mozilla Firefox, and Internet Explorer do not support this type of filtering.

For end user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). You can also tell users to review [What can my IT admin see on my device](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](end-user-educate.md).

## Next steps

- [Considerations when managing Windows devices using Intune on Azure](/intune-classic/deploy-use/intune-on-azure).
