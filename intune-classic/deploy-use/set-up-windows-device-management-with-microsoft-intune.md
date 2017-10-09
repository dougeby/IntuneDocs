---
# required metadata

title: Set up Windows device management with Microsoft Intune 
description: Enable mobile device management (MDM) for Windows devices with Microsoft Intune.
keywords:
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Set up Windows device management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic helps IT administrators simplify Windows enrollment for their users.  Windows devices can be enrolled without any additional steps, but you can make enrollment easier for users.

Two factors determine how you can simplify Windows device enrollment:
- **Do you use Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is included with Enterprise Mobility + Security and other licensing plans.
- **What versions of Windows clients will enroll?** <br>Windows 10 devices can automatically enroll by adding a work or school account. Earlier versions must enroll using the Company Portal app.

||**Azure AD Premium**|**Other AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatic enrollment](#enable-windows-10-automatic-enrollment) |[User enrollment](#enable-windows-enrollment-without-automatic-enrollment)|
|**Earlier Windows versions**|[User enrollment](#enable-windows-enrollment-without-automatic-enrollment)|[User enrollment](#enable-windows-enrollment-without-automatic-enrollment)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Enable Windows enrollment without automatic enrollment
You can let users enroll their devices without Azure AD Premium automatic enrollment. Once you assign licenses, users can enroll after adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure AD. Creating a DNS alias (CNAME record type) makes it easier for users to enroll their devices. If you create DNS CNAME resource records, users connect and enroll in Intune without having to enter the Intune server name.

**Step 1: Create CNAMEs** (optional)<br>
Create CNAME DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com.

Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users. If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, enrollment.manage.microsoft.com.

If there is more than one verified domain, create a CNAME record for each domain. The CNAME resource records must contain the following information:

CNAME resource records must have the following information:

|TYPE|Host name|Points to|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

`EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

If your company uses multiple domains for user credentials, create CNAME records for each domain.

For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

**Step 2: Verify CNAME** (optional)<br>
In the [Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Mobile Device Management** &gt; **Windows**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

## Tell users how to enroll Windows devices
Tell your users how to enroll their Windows devices and what to expect after they're brought into management.
For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). You can also send users to [What can my IT admin see on my device](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](/intune/end-user-educate).

### See also
[Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md)
