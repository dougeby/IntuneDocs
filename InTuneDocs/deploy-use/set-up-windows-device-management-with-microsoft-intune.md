---
# required metadata

title: Set up Windows device management with Microsoft Intune | Microsoft Docs
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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Set up Windows device management

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use one of the following methods to set up enrollment for Windows devices:

- [**Windows 10 automatic enrollment with Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  This method is only available for Windows 10 devices.
 -  You must have Azure Active Directory Premium to use this method.
 -  If you choose not to enable automatic enrollment, use the enrollment method for Windows 8.1 and Windows Phone 8.1.

- [**Enrollment without Azure AD Premium automatic enrollment**](#enable-windows-enrollment-without-azure-ad-premium)
 - You must use this method to enroll Windows 8.1 and Windows Phone 8.1 devices.
 - You can use this method for Windows 8.1 and later devices if you don't want to use Azure Active Directory (AD) Premium.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Enable Windows enrollment without automatic enrollment
You can let users install and enroll their devices without Azure AD Premium automatic enrollment. Once you assign a license to users' account, the user can add that account to a Windows device and agree to enroll the device in management. If you create DNS CNAME resource records,  users connect and enroll in Intune without entering a server name.

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
In the [Intune administration console](http://manage.microsoft.com), choose **Admin** &gt; **Mobile Device Management** &gt; **Windows**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

## Tell users how to enroll Windows devices
Tell your users how to enroll their Windows devices and what to expect after they're brought into management.
For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). You can also send users to [What can my IT admin see on my device](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### See also
[Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md)
