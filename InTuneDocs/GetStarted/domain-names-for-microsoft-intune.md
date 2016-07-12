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



# Custom domain names with Microsoft Intune

The steps to add and verify a custom domain can alternatively be [performed in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

When your organization signs up for a Microsoft cloud-based service like Intune, you're given an initial domain name hosted in Azure Active Directory that looks like the following: **yourdomain.onmicrosoft.com**. In this example, **yourdomain** is the domain name that you chose when you signed up, and **onmicrosoft.com** is the suffix assigned to the accounts you add to your subscription.

You cannot rename or remove that initial domain name. However, you can add, verify or remove your own custom domain names to use with Intune, which is helpful if you want to keep your business identity.

## To add and verify your custom domain 

1. Go to [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) and sign into your administrator account.
	> [!IMPORTANT]
	> Check 
	[Intune Account Portal has merged with the Office 365 management portal](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) announcement for more details on where to manage Microsoft Intune users, groups, and domains.
2. In the navigation pane, choose **Settings** &gt; **Domains**.
3. Choose **Add domain**, and type your custom domain name.
4. The **Verify domain** dialog box opens giving you the values to create the TXT record in your DNS hosting provider.
	- **GoDaddy users**: Office 365 Management portal redirects you to GoDaddy's login page. After you enter your credentials and accept the domain change permission agreement, the TXT record is created automatically. You can alternatively [create the TXT record](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
	- **Register.com users**: Follow the [step-by-step instructions](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) to create the TXT record.

	> [!TIP] Make sure to create a DNS alias (CNAME) for [Windows devices enrollment](https://docs.microsoft.com/en->us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune), while making changes in your DNS hosting provider.

In a hybrid cloud scenario, after you added your custom domain name, and it has been verified that your organization owns it, you can keep managing user accounts in your on-premises Active Directory, then synchronize it with Azure AD.

## To synchronize on-premises users with Azure AD##

1. [Add the UPN suffix](https://technet.microsoft.com/en-us/library/cc772007.aspx) for your custom domain in your on-premises Active Directory.
2. Set the new UPN suffix for the on-premises users that you plan to import.
3. Run [Azure AD Connect sync](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) to integrate your on-premises users with Azure AD.
4. Once the user account information has successfully synchronized, you can then assign Microsoft Intune licenses using the [Office 365 Management Portal](https://portal.office.com/Admin/Default.aspx).

### See also

[About your initial onmicrosoft.com domain in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)
