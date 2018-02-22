---
# required metadata

title: Integrate Zimperium with Intune
titleSuffix: Intune on Azure
description: "Integrate Intune with Zimperium"
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Integrate Zimperium with Intune

Complete the following steps to integrate the Zimperium Mobile Threat Defense solution with Intune.

## Before you begin

> [!NOTE]
> The following steps are to be completed in the [Zimperium MTD console](https://staging2-console.zimperium.com).

Before starting the process of integrating Zimperium with Intune, make sure you have the following:

-   Microsoft Intune subscription

-   Azure Active Directory admin credentials to grant the following permissions:

    -   Sign in and read user profile

    -   Access the directory as the signed-in user

    -   Read directory data

    -   Send device information to Intune

-   Admin credentials to access Zimperium MTD console.

### Zimperium app authorization

The Zimperium app authorization process follows:

-   Allow the Zimperium service to communicate information related to device health state back to Intune.

-   Zimperium syncs with Azure Active Directory (AD) Enrollment Group membership to populate its device’s database.

-   Allow Zimperium admin console to use Azure AD Single Sign On (SSO).

-   Allow the Zimperium app to sign in using Azure AD SSO.

## To set up Zimperium integration

1.  Go to [Zimperium MTD console](https://staging2-console.zimperium.com) and sign in with your credentials.

2.  Choose **Management** from the left menu.

3.  Choose the **MDM settings** tab.

4.  Choose **Add MDM,** then select **Microsoft Intune** from the **MDM provider** list.

5.  After you set Microsoft Intune as the MDM service, the **Microsoft Intune Configuration** window pops up, choose the **Add Azure Active Directory** for each option: **Zimperium zConsole**, **zIPS iOS and Android apps** to authorize Zimperium to communicate with Intune and Azure AD through Azure AD Single Sign-On.

	> [!IMPORTANT]
	> You must add the Zimperium zConsole, zIPS iOS and Android apps to complete to the integration process with Intune.

6.  Choose **Accept** to authorize the Zimperium app to communicate with Intune and Azure Active Directory.

7.  After you added the **Zimperium zConsole** and the **zIPS iOS and Android** apps to Azure AD, add the Azure AD security groups. This allows Zimperium to synchronize the Azure AD security group with its service.

8.  Choose **Finish** to save the configuration and start the first Azure AD security group synchronization.

## Next steps

-   [Set up Zimperium apps](mtd-apps-ios-app-configuration-policy-add-assign.md)
