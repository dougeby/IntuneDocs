---
# required metadata

title: Supported mobile devices and browsers | Microsoft Intune
description: Mobile devices and computers that Intune supports
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Supported devices and browsers for Intune

You can enroll then manage the following device types:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Enrolling devices provides [these capabilities](/Intune/get-started/choose-how-to-manage-devices).

Alternatively, you can manage Windows PCs with the Intune PC client software. The Intune PC client software supports Windows 7 and later, except Windows 10 Home. Managing PCs with the client software provides [these capabilities](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Customers with Enterprise Management Suite can also use Azure Active Directory (Azure AD) to register Windows 10 devices.

## Microsoft Intune supported web browsers

Different administrative tasks require you to use one of the following administrative websites.

- [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge and mobile browsers are not supported for the admin console because they do not support [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). The Intune console is moving from the Silverlight experience over a period of time; eventually, all of Intune's mobile device and application management features will be [made available in the new Microsoft Azure portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Intune feature |Supported browsers|
|---------|---------|
|Intune Admin console     |  Internet Explorer 10 or later<br /><br />Google Chrome (versions prior to version 42)<br /><br />Mozilla Firefox with Silverlight enabled<br />**Note:** Mozilla will remove support for Silverlight effective March 2017. [Learn more](https://go.microsoft.com/fwlink/?linkid=836872).<br /><br />Microsoft Edge and mobile browsers are not supported for the Admin console.                      
|Office 365 Admin Portal     |All browsers, including mobile browsers and managed browsers  |
|Company Portal website     |**On mobile devices:** use the default web browser for each supported platform   <br /><br />**On Windows PCs:** Internet Explorer 10 or later, or Microsoft Edge<br /><br />**On Mac OS X 10.9 or later:** Apple Safari    |

> [!Note]
> Microsoft Edge and mobile browsers are not supported for the admin console because they do not support [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). The Intune console is moving from the Silverlight experience over a period of time; eventually, all of Intune's mobile device and application management features will be [made available in the new Microsoft Azure portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**As a tenant administrator, use this portal to manage your subscription**, including the following tasks, when permitted by your administrator role:

- Manage user accounts for the subscription, and configure directory synchronization from your on-premises Active Directory.
- Manage groups of users, called security groups.
- Assign licenses to use Intune to users.
- Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with.
- Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.
- Find links to view the health of the Intune service.
- As a tenant administrator, you can sign in to the Office 365 portal to manage the subscription, even when your account is not assigned a license to use Intune.
- Any users who have a license to Intune, but who are not administrators, can use this portal to reset their account password and edit their profile.
- To access the Office 365 portal, your account must have a sign-in status of **Allowed**. This status is different from having a license to the subscription. By default, all user accounts are **Allowed**.


### [Microsoft Intune administrator console](https://manage.microsoft.com/)

**As a service administrator, use this portal to manage day-to-day operations** including:

- Set policies for computers and mobile devices.
- Upload and deploy software like software updates and apps.
- Manage Endpoint Protection on computers.
- View device status and run reports.
- Sign in to this portal. You must have either service administrator permissions or be a tenant administrator with the global administrator role to sign in to this portal.


Only users with service administrator permissions or tenant administrators with the global administrator role can sign in to this portal. To access the administration console, your account must have a license to use Intune and a sign-in status of **Allowed**.
