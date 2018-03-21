---
# required metadata

title: Prerequisites for MAM policies 
description: This topic describes the prerequisites for setting up users before you create mobile app management policies.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/29/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Get ready to configure app protection policies in the Azure portal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic describes the prerequisites and the steps you must complete **before** you can create app protection policies in the Azure portal.

To understand how Intune app protection policies can protect your company data, see [Protect apps and data using app protection policies](protect-apps-and-data-with-microsoft-intune.md).

## What is the Azure portal?

The Azure portal is the new admin console for creating app protection policies. It supports the following MAM scenarios:
- Devices that are enrolled in Intune
- Devices that are managed by another Mobile Device Management (MDM) solution
- Devices that are not managed by any MDM solution (BYOD)

Currently, both the **Intune administrator console** and the **Azure portal** enable you to configure app protection policies.  Consider the following:

* The policies that you create on the **Azure portal** are supported for **all MAM scenarios** that are listed previously. The **Intune administrator console** only supports creating policies for **devices that are enrolled and managed by Intune**.

* You might not see all app policy settings in the Intune administrator console because **new settings** can only be added to the **Azure portal**.

* If you create app protection policies in **both** the Intune admin console and the Azure portal, the policy in the **Azure portal is applied to the apps and deployed to users**.
    * App protection policies that are created in the Intune admin console cannot be imported into the Azure portal.  The app protection policies must be re-created in the Azure portal.


* Other **app management features**, such as deploying apps and app configuration policies, are currently only available in the **Intune administrator console**.


If you are new to the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get the basics of using the Azure portal.

For instructions about how to create an app policy on the Intune admin console, see [Configure and deploy app protection policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Supported platforms
- iOS 8.1 or later
- Android 4 or later
- Windows 10

>[!NOTE]
>Beginning with version 1703, app protection policies can be defined for Windows 10 devices in the MAM without enrollment scenario. For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Supported apps
* **Microsoft apps:** These apps have the Intune App SDK built in and require no further processing before you apply app protection policies.
To see the full list of supported Microsoft apps, go to the [Microsoft Intune mobile application gallery](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page. Click an app to see the supported scenarios and platforms, and to see whether the app supports multiple identities.

* **Your organization's line-of-business apps:** You must prepare these apps to include the Intune App SDK before you can apply app protection policies.

  * For devices that are managed by Intune, see [Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management).

  * For devices that are not managed (such as employee-owned devices), or for devices that are managed by another mobile device management solution, see [Protect line-of-business apps and data on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Prerequisites

-   **A Microsoft Intune subscription**. Users need Intune licenses to get apps that have app protection policies.
You   already have an Intune subscription if you are currently using Intune to manage your devices. You also have an Intune subscription if you have purchased an Enterprise Mobility Suite (EMS) license. If you are trying Intune to check out the MAM capabilities, you can get a trial account on the [Microsoft Intune page](https://www.microsoft.com/server-cloud/products/microsoft-intune/).

    To verify if you have an Intune subscription, in the Office portal, go to the **Billing** page.  If you have a subscription, you should see Intune as **Active** in the subscriptions.

-   **An Office 365 subscription**, which is required for the following:

  - To apply app protection policies to apps with multiple-identity support.

  - To create SharePoint Online and Exchange Online work
 accounts. Exchange on-premises and SharePoint on-premises are not supported.

-   **Skype for Business Online setup for modern authentication**. For more information, see [Enable modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) to create users. Azure AD authenticates users when they open the app and enter their work credentials.

    > [!NOTE]
    > User groups must be set up in Azure AD. Intune user groups cannot be used to deploy app protection policies in the Azure portal.

### Create users and assign Microsoft Intune licenses

1.  Sign in to the [Office portal](https://portal.office.com) with your admin credentials.

2.  Add users as described in the **Steps to complete a 30-day evaluation of Intune** section of the [Intune evaluation guide](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), and then assign Intune licenses. To give a user the ability to access the Office portal, the Azure AD portal, and the Azure  portal, assign the **Global administrator** role to the user.

5.  App protection policies are deployed to user groups in Azure Active Directory. To create user groups for your app protection policies, create a user group as described in the **Create a user group** section of [Create groups to organize evaluation subscription users and devices](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### Assign roles to non-global admin users

Global administrators have access to the [Azure portal](https://portal.azure.com).  If you want users who are not global administrators to be able to configure policies and do other mobile app management tasks, check the [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) article.

## Next steps
[Create and deploy app protection policies with Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
