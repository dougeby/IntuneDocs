---
# required metadata

title: Prerequisites for MAM policies | Microsoft Intune
description: This topic describes the pre-requisites and setting up users before you can create mobile app management policies.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Get ready to configure mobile app management policies on the Azure portal
This topic describes the prerequisites and the steps you must complete **before** you can create mobile app management (MAM) policies in the Azure portal.

To understand how Intune MAM policies can protect your company data, see [Protect apps and data using mobile app management policies](protect-apps-and-data-with-microsoft-intune.md).

## What is the Azure portal?
The Azure portal is the new admin console for creating MAM policies and supports the following MAM scenarios:
- **Devices that are enrolled in Intune**
- **Devices that are managed by a another MDM solution**
- **Devices that are not managed by any MDM solution (BYOD)**


Currently, both the **Intune administrator console** and the **Azure portal** allow you to configure MAM policies.  Consider the following:

* The policies that you create on the **Azure portal** is supported for **all MAM scenarios** listed above. The **Intune administrator console** only supports creating policies for **devices that are enrolled and managed by Intune**.
* You may not see all MAM policy settings in the Intune administrator console as **new settings** may only be added to the **Azure portal**.
* If you create MAM policies in **both** the Intune admin console and the Azure portal, the policy in the **Azure portal is applied to the apps and deployed to users**.
    * MAM policies that are created in the Intune admin console cannot be imported into the Azure portal.  The MAM policies must be re-created in the Azure portal.
* Other **app management features** like deploying apps and app configuration policies are currently only available in the **Intune administrator console**.


If you are new to Azure portal, read the [Azure portal for Microsoft Intune MAM policies](azure-portal-for-microsoft-intune-mam-policies.md) topic to get the basics of using the Azure portal.

For instructions on how to create a MAM policy on the Intune admin console, see [Configure and deploy mobile application management policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Supported platforms
- iOS 8.1 or later

- Android 4 or later

>[!NOTE]
>Windows devices don’t support these mobile application management policies. However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality. For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Supported apps
* **Microsoft apps:** These apps have the Intune App SDK built in and require no further processing before you apply MAM policies.
To see the full list of supported Microsoft apps, go to the [Microsoft Intune mobile application gallery](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page. Click an app to see the supported scenarios and platforms, and to see whether the app supports multiple identities.
* **Your organization's line-of-business apps:** These require preparing the apps to include the Intune App SDK before you can apply MAM policies.

  * For devices that are managed by Intune, see [Decide how to prepare apps for MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * For devices that are not managed (like employee-owned devices), or for devices that are managed by another mobile device management solution, see [Protect line-of-business apps and data on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Prerequisites

-   A subscription to Microsoft Intune.    Users need [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] licenses to get apps that have MAM policies.
You   already have an [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] subscription if you are currently using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to manage your devices.  You also have an [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] subscription if you have purchased an Enterprise Mobility Suite (EMS) license. If you are trying [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to check out the MAM capabilities, you can get a trial account on the [Microsoft Intune webpage](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    To check whether you have an [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] subscription, in the Office portal, go to the **Billing** page.  You should see [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] as **Active** in the subscriptions.

-   An Office 365 subscription, which is required for the following:
  - To apply MAM policies to apps with multiple-identity support.
  - To create  SharePoint Online and Exchange Online work accounts. Exchange on-premises and SharePoint on-premises are not supported.
-   Skype for Business Online setup for modern authentication. For more information, see [Enable modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) to create users. Azure AD authenticates users when they open the app and enter their work credentials.

    > [!NOTE]
    > User groups must be setup in Azure AD. Intune user groups cannot be used to deploy MAM policies in the Azure portal.

### Create users and assign Microsoft Intune licenses

1.  Sign in to the   [Office portal](http://portal.office.com) with your admin credentials.

2.  Add users as described in the **Add users** section of [this](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) topic and assign Intune licenses. To give a user the ability to access the Office portal, the Azure AD portal, and the Azure  portal, assign the **Global administrator** role to the user.

5.  MAM policies are deployed to user groups in Azure Active Directory. To create user groups for your MAM policies, create a user group as described in the **Create a user group** section of [this](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) topic.

### Non-Global admin users

Global administrators have access to the [Azure portal](https://portal.azure.com).  If you want users who are not Global administrators to be able to configure policies and do other mobile app management tasks, you can assign the contributor role to the users. For detailed instructions, see [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

The following table lists the roles and permissions that you can assign to admin users.

|||
|--|----|
|**Role**|**Permissions**|
|Global administrator (Office 365 portal)|Access to the Office 365 portal and the Azure AD portal.<br /><br />Access to the Azure  portal (can do both role management and mobile app management tasks).|
|Owner (Azure  portal)|Access to the Azure  portal (can do both role management and mobile app management tasks).|
|Contributor (Azure  portal)|Access to the Azure  portal (can do only the mobile app management tasks).|




## Next steps
[Create and deploy mobile app management policies with Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
