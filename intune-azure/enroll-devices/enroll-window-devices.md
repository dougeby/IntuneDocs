---
# required metadata

title: Enroll Windows devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Enable Intune mobile device management (MDM) for Windows devices."
keywords:
author: staciebarker
manager: stabar
ms.date: 02/08/17
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
#ms.custom:

---

# Enroll Windows devices 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use one of the following methods to set up enrollment for Windows devices:

- **[Windows 10 and Windows 10 Mobile automatic enrollment with Azure Active Directory Premium](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  This method is applicable only for Windows 10 and Windows 10 Mobile devices.
 -  You must have Azure Active Directory Premium to use this method. Otherwise, use the enrollment method for Windows 8.1 and Windows Phone 8.1.
 -  If you choose not to enable automatic enrollment, use the enrollment method for Windows 8.1 and Windows Phone 8.1.


- **[Windows 8.1 and Windows Phone 8.1 enrollment by configuring CNAME](#set-up-windows-8.1-and-windows-phone-8.1-enrollment-by-configuring-cname)** 
 - You must use this method to enroll Windows 8.1 and Windows Phone 8.1 devices.


## Prerequisites

If some of the following prerequisites aren't in the Intune Azure preview yet, you'll need to do them from the classic Intune admin console.

- [Configure a custom domain name](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Set the mobile device management (MDM) authority](set-mdm-authority.md) as **Microsoft Intune**
- [Configure the Company Portal app](/intune-azure/manage-apps/company-portal-app.md)
- Assign licenses to users

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Set up Windows 8.1 and Windows Phone 8.1 enrollment by configuring CNAME

You can let users install and enroll their devices by using the Intune Company Portal. If you create DNS CNAME resource records,  users connect and enroll in Intune without entering a server name.

1. **Create CNAMEs** (optional)<br>
 Create **CNAME** DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment.manage.microsoft.com.

	Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users. If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, manage.microsoft.com.

	If you currently have a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com, we suggest that you replace it with a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com. This change is recommended, because the manage.microsoft.com endpoint is being deprecated for enrollments in a future release.

	If there is more than one verified domain, create a CNAME record for each domain. The CNAME resource records must contain the following information:

	CNAME resource records must have the following information:

  |TYPE|Host name|Points to|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

  `EnterpriseRegistration.windows.net` – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory by using their work or school account

  If your company uses multiple domains for user credentials, create CNAME records for each domain.

  For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Changes to DNS records might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

2.  **Verify CNAME**<br>In the [Intune administration console](http://manage.microsoft.com), choose **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**. Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.

3.  **Optional steps**<br>The **Add Sideloading keys** step is not needed for Windows 10. <br>The **Upload Code-Signing Certificate** step is needed only if you are distributing to devices the line-of-business (LOB) apps that are not available from the Windows Store.

4.  **Tell your users how to enroll their devices and what to expect after their devices are under management.**

	For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). You can also send users to [What can my IT admin see on my devic](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

	For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

No additional work is required unless you will deploy the Company Portal to devices.  Steps 2 and 3 in the admin console can be safely ignored.
