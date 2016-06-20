---
# required metadata

title: Domain names for Microsoft Intune | Microsoft Intune
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Managing domains with Microsoft Intune

Before you set up Microsoft Intune, review this topic and other requirements listed in [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

When your organization signs up for a Microsoft cloud-based service such as Intune, you are given an initial domain name hosted in Azure Active Directory that looks like the following: **yourdomain.onmicrosoft.com**. In this example, **yourdomain** is the domain name that you chose when you signed up, and **onmicrosoft.com** is the suffix assigned to the accounts you add to your subscription. 

After you complete the sign-up process, you cannot rename or remove that initial domain name. However, you can add, verify or remove your own custom domain names to use with Intune.

By default, when you use the onmicrosoft domain, each user you import to Azure Active Directory, receives the **onmicrosoft.com** suffix for their user principal name (UPN). If you decide to go with your own custom domain, you need to [add the UPN suffix](https://technet.microsoft.com/en-us/library/cc772007.aspx), set the new UPN suffix for the users you plan to import in your on-premises Active Directory, then run [Azure AD Connect sync](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) to integrate your on-premises identities with Azure Active Directory.

Once the directory synchronization cycle is completed, the objects will be available on the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx), which now hosts Intune users and groups.

> [!NOTE]
> Please read 
[Intune Account Portal has merged with the Office 365 management portal](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) announcement for more details on where to manage Microsoft Intune users and groups.

## To add and verify your domain 

1. Go to [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) and sign into your administrator account.
2. In the navigation pane, choose **Settings** &gt; **Domains**.
3. Choose **+ Add domain**, and type your *custom domain name*.
4. The **Verify domain** dialog box opens giving you information to create the TXT record in your DNS hosting provider.
5. Follow the step-by-step instructions for [Register.com](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) or [GoDaddy](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US), to add the TXT record at your DNS hosting provider based on the values provided on step 4.

After you added your custom domain name, and it has been verified that your organization owns it, you can keep managing user accounts and groups in your on-premises Active Directory, then synchronize it with Azure Active Directory. Users and groups can also be created directly in Azure Active Directory, but these objects will not be synchronized with the on-premises environment.

You can also add your custom domains from Azure Active Directory. Please check [Add a custom domain name to Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/) for more details.

## DNS alias (CNAME) 

The CNAME record is used as part of the [enrollment process](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune). When this DNS entry is configured, the DNS server redirects your *EnterpriseEnrollment.CompanyDomainName.com* to *manage.microsoft.com*. For example, if user's e-mail address is *user@contoso.com*, you have to create a CNAME in DNS that redirects *EnterpriseEnrollment.contoso.com* to *manage.microsoft.com*.

Although the CNAME DNS entry is optional for device enrollment, it is recommended to create one or more records when necessary, to make things easier during the device enrollment process. If no CNAME record is found, the user is prompted to enter the MDM server name manually.

### See also

[About your initial onmicrosoft.com domain in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)
