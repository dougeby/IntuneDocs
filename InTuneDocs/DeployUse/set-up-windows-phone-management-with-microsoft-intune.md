---
title: Set up Windows 10 Mobile and Windows Phone management with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 61e9b6c3-8795-49b0-8ab2-a9a05ee3ea1f
author: NathBarn
---

## Set up Windows Phone and Windows 10 Mobile management with Microsoft Intune
Before you can manage Windows 10 Mobile or Windows Phone devices with Microsoft Intune, the devices must be able to communicate with Intune. To simplify this, you can create a DNS record so users don't have to enter the server address.  

For most scenarios, users can install the Company Portal app from the Windows Store. If you manage Windows Phone 8.0 devices or need to deploy the Company Portal to Windows Phone devices, you must also download and sign the Company Portal app. See [Set up Windows Phone 8.0 management](set-up-windows-8.0-management-with-microsoft-intune.md).


## Set up Windows 10 Mobile and Windows Phone management  
1.  **Set up Intune**
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](https://technet.microsoft.com/library/mt346013.aspx) as **Microsoft Intune** and setting up MDM.

2.  **Set a DNS alias for the enrollment server address** (optional)

    Creating a DNS alias (CNAME record type) makes it easier for users to enroll their devices. If you don't create a DNS alias, users must

  1.  Create **CNAME** DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain.The CNAME resource records must contain the following information:

      |TYPE|Host name|Points to|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

      DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

      **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

      **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

    2.  In the [Intune administration console](http://manage.microsoft.com), click **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**.

      ![](../media/Windows-Device-Enrollment.png)

    3.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.



No additional work is required unless you will deploy the Company Portal to devices.  Steps 2, 3 and 4 in the admin console can be safely ignored.
