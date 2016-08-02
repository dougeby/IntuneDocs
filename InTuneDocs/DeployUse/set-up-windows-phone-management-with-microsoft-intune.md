---
# required metadata

title: Set up Windows 10 Mobile and Windows Phone management | Microsoft Intune
description: Enable mobile device management (MDM) for Windows 10 Mobile or Windows Phone devices with Microsoft Intune.
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Set up Windows Phone and Windows 10 Mobile management with Microsoft Intune
To set up your Windows device, you can find help [here](../end-user/using-your-windows-device-with-intune.md).

Before you can manage Windows 10 Mobile or Windows Phone devices with Microsoft Intune, the devices must be able to communicate with Intune. To simplify this, you can create a DNS record so users don't have to enter the server address. The steps below describe how to simplify enrollment for users.  

For most scenarios, users can install the Company Portal app from the Windows Store. If you manage Windows Phone 8.0 devices or need to deploy the Company Portal to Windows Phone devices, you must also download and sign the Company Portal app. See [Set up Windows Phone 8.0 management](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Set up Intune**
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) as **Microsoft Intune** and setting up MDM.

2.  **Set a DNS alias for the enrollment server address** (optional)

    Creating a DNS alias (CNAME record type) makes it easier for users to enroll their devices. Although the CNAME DNS entry is optional for Windows device enrollment, it is recommended to create one or more records when necessary, to make things easier during the Windows device enrollment process. If no CNAME record is found, the user is prompted to enter the MDM server name manually.

  1.  Create **CNAME** DNS resource records for your company’s domain. For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain.The CNAME resource records must contain the following information:

      |TYPE|Host name|Points to|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Hour|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Hour|

      DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

      **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

      **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

    2.  In the [Intune administration console](http://manage.microsoft.com), click **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**.

      ![Set up mobile device management for Windows dialog box](../media/windows-device-enrollment.png)

    3.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.

    4.  Your users will need to know how to enroll their devices and what to expect once they're brought into management.
        - [What to tell your end users about using Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
        - [End user guidance for Windows devices](../end-user/using-your-windows-device-with-intune.md)



No additional work is required unless you will deploy the Company Portal to devices.  Steps 2 and 3 in the admin console can be safely ignored.
