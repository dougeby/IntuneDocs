---
# required metadata

title: Set up Windows device management with Microsoft Intune | Microsoft Intune
description: Enable mobile device management (MDM) for Windows PCs including Windows 10 devices with Microsoft Intune.
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
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
#ms.custom:

---

# Set up Windows device management
To set up your Windows device, you can find help [here](../enduser/using-your-windows-device-with-intune.md).

With Intune, you can enable BYOD ("bring your own device") for Windows PC device enrollment to give access to company email and apps. Used with Azure Active Directory, this also provides a fast, no-touch way to bring new Windows 10 devices into management and gain access to company resources without having to reimage the computer. Once enrolled, users can log in and their devices can be targeted with policy, apps, and settings using the Intune administration console. You may also want to [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) or [manage computers with Intune client software](manage-windows-pcs-with-microsoft-intune.md) using the Intune client.

Creating a DNS CNAME helps users connect and enroll in Intune without entering a server name.

### Set up Windows device management

  1.  Create **CNAME** DNS resource record for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Although the CNAME DNS entry is optional for Windows device enrollment, it is recommended to create one or more records when necessary, to make things easier during the Windows device enrollment process. If no CNAME record is found, the user is prompted to enter the MDM server name manually.

  If there is more than one verified domain, create a CNAME record for each domain. The CNAME resource records must contain the following information:

  |TYPE|Host name|Points to|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

  DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

  **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

  **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  In the [Intune administration console](http://manage.microsoft.com), click **Admin** &gt; **Mobile Device Management** &gt; **Windows**.
  ![Windows device management dialog box](../media/enroll-intune-winenr.png)

  3.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.

  4.  Your users will need to know how to enroll their devices and what to expect once they're brought into management.
      - [What to tell your end users about using Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [End user guidance for Windows devices](../enduser/using-your-windows-device-with-intune.md)

### See also
[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)
