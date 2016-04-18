---
title: Start with a paid subscription to Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
author: Staciebarker
---

# Start with a paid subscription to Microsoft Intune
This walkthrough leads you through the steps of setting up paid subscription of [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] to quickly and easily begin managing mobile devices and Windows PCs in use by your organization. You can follow each step in order or just skip ahead if a step is not applicable to your specific environment or business needs.

>[!NOTE]
>This article focuses on setting up Intune as a standalone service. Alternatively, if you're currently using Microsoft System Center Configuration Manager to manage computers and servers, you can [extend Configuration Manager to manage mobile devices](https://technet.microsoft.com/library/jj884158.aspx) by connecting Intune with Configuration Manager in a hybrid MDM deployment to manage mobile devices too.

Getting started with a paid subscription of Intune shares many of the same steps as starting with a [free 30-day trial](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). However, after your trial, and when you are ready to start managing your mobile devices, you will need to address several additional requirements. These will vary depending on your current network infrastructure and business requirements including:

-   Synchronizing on-premises Active Directory accounts with Intune and Azure Active Directory

-   Updating public domain and DNS service records with your domain registrar

-   Customizing Intune features for production use

>[!TIP]
>If you purchase at least 150 licenses for Microsoft Intune in an eligible plan, you can use the "FastTrack Center Benefit," a service where Microsoft specialists work with you to get your environment ready for Intune. See [Microsoft Intune Service Benefit Description](https://technet.microsoft.com/library/mt228265.aspx).

<!-- this section is unnecessary due to expand/collapse functionality

## About this guide
There are 9 steps in this guide, not including post-configuration tasks. Total time to read through these steps is about 30 minutes, or you can jump to a specific step.
1. [Sign into Intune](get-started-with-a-paid-subscription-to-microsoft-intune-step-1.md)
2. [Configure a custom domain name](get-started-with-a-paid-subscription-to-microsoft-intune-step-2.md)
3. [Synchronize Active Directory and add users](get-started-with-a-paid-subscription-to-microsoft-intune-step-3.md)
4. [Manage Intune licenses](get-started-with-a-paid-subscription-to-microsoft-intune-step-4.md)
5. [Organize users and devices](get-started-with-a-paid-subscription-to-microsoft-intune-step-5.md)
6. [Create policies and publish an app](get-started-with-a-paid-subscription-to-microsoft-intune-step-6.md)
7. [Customize the Company Portal](get-started-with-a-paid-subscription-to-microsoft-intune-step-7.md)
8. [Enroll computers](get-started-with-a-paid-subscription-to-microsoft-intune-step-8.md)
9. [Enroll mobile devices and install an app](get-started-with-a-paid-subscription-to-microsoft-intune-step-9.md)

[Post-configuration tasks](post-configuration-tasks.md)

-->

## Before you begin
Starting with a paid subscription means that you're ready to deploy Intune and make changes to your existing network infrastructure. This could range from simply adding or updating your internal and external DNS records to synchronizing your existing Active Directory user accounts to Azure Active Directory. Whatever mix of Intune  mobile device management features you decide on, you'll need to  carefully plan how Intune will interact with your existing network components and services. Specifically, you should review:

-   **How you'll manage user identity**:  For most medium to large sized organizations, connecting your existing directory services to Intune via Azure Active Directory is the best and most convenient way to manage user identity with Intune. This is especially true if you already use other Microsoft cloud services, such as Office 365 or Exchange Online. Synchronizing your existing user accounts using [Microsoft's AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) is a quick and easy way to connect your on-premises Active Directory to Azure Active Directory and configure a single sign-on authentication experience for your users.

-   **How DNS will be impacted**: If you want to use your own domain name instead of the default onmicrosoft.com domain you get when first signing up for Intune, some public DNS record updates will be needed. DNS record updates are required so that mobile devices can locate the Intune service and ensure the management service for your subscription works correctly to manage all devices in use by your organization.

## Have the following items handy
Ready to get started? You'll need the following items when starting to use your paid subscription to Intune:

### A device with a Silverlight-enabled web browser
You will need this to access the Intune administration console where you'll manage devices, apps, and policies. You will also need a web browser to access the web-based company portal when not accessing the company portal app from a mobile device. To make things easier, you can use the “privacy mode” setting on the same browser that you use for [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] administration (for example: in Internet Explorer, you can click **Tools** &gt; **InPrivate Browsing**).

>[!TIP]
>Because of this requirement, the Microsoft Edge browser is not supported for accessing the Intune administration console.

<!-- you get one of these when you sign up for Intune so they'll already have this. It's also discussed in the steps (and this is definitely not a trial!)

### Microsoft Online Services account
If you have an existing Microsoft Online Services account, you'll need the **administrator credentials** for that account. If you don’t have such an account you will need to get one wi.
-->

### Certificates for mobile devices
If you'll manage iOS or Windows Phone devices with Intune, you'll need certificates and accounts to retrieve those certificates. You won't need any additional certificates to manage Android devices.

- No certificate is required for **Windows Phone 8.1** users who install the company portal app from the Store. However, a [Symantec code signing certificate](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) is required for **Windows Phone 8.0** or to use Intune to deploy the company portal app to Windows Phone 8.1 devices.

>[!NOTE]
>This getting started walkthrough assumes your users get the company portal app from the Store on a Windows Phone 8.1 or later device. For information about Windows Phone 8.0 support, see [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

- There are no certificate requirements for **Windows PCs** or **Windows RT devices** when [enrolling Windows PCs as devices](/intune/enduser/enroll-your-device-in-intune-windows) or  [installing the Windows PC client for Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).

- For **iOS** or **Mac OS X** devices you will need to request an Apple Push Notification service certificate from Apple, as described in [Set up iOS and Mac management with Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

## Next steps
It's time to get started with your paid subscription!

>[!div class="step-by-step"]
[**Sign in to Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-1)
