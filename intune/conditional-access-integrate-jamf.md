---
# required metadata

title: Integrate Jamf Pro with Intune conditional access
titlesuffix: "Azure portal"
description: "Use conditional access to help secure Jamf-managed devices."
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6

# optional metadata

#ROBOTS: NOINDEX, NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: elocholi
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Integrate Jamf Pro with Intune conditional access

[!INCLUDE][azure_portal](./includes/azure_portal.md)]

[!INCLUDE][macos-preview-1708](/intune-user-help/includes/macos-preview-1708.md]

If your organization uses [Jamf Pro](https://www.jamf.com) to manage your end users' Macs, you can use Microsoft Intune and Azure Active Directory to apply [conditional access](conditional-access.md) policies. This ensures that your end users are compliant with your organizations policy for accessing confidential information.

## Prerequisites

You need the following to configure conditional access with Jamf Pro:

- Access to the Intune Private Preview for macOS conditional access
- Jamf Pro 10.1.0 or later
- [Company Portal app for macOS](https://aka.ms/macoscompanyportal)
- macOS devices with OS X 10.11 Yosemite or later

## Connecting Intune to Jamf Pro

You can connect Intune with Jamf Pro by:

1. Creating a new application in Azure
2. Enabling Intune to integrate with Jamf Pro
3. Configure conditional access in Jamf Pro

### Create a new application in Azure

1. Open **Azure Active Directory** > **App Registration**.
2. Click **+New application registration**.
3. Enter a **display name**, such as **Jamf Conditional Access**.
4. Select **Web app / API**.
5. Specify the **Sign-On URL** for Jamf Pro.
6. Click **Create application**.
7. Save the newly-created **Application ID**, then open **All Settings** > **Keys** to create a new Application Key. Save the Application Key.

  > [!NOTE]
  > The Application Key is only shown once during this process. Be sure to save it somewhere where you can easily retrieve it.

8. Navigate to **All Settings** > **API Access** > **Required Permissions** and delete all permissions.

  > [!NOTE]
  > Add a new required permission. The application can have only work properly if it has the single required permission.

9.  Select **Microsoft Intune API** and click **Select**.
10. Choose **Send device attributes to Microsoft Intune** and click **Select**.
11. Click the **Grant Permissions** button after saving the required permissions for the application.

  > [!NOTE]
  > If the Application Key expires, you must create a new Application Key in Microsoft Azure and then update the Conditional Access data in Jamf Pro. Azure allows you to have both the old key and new key active to prevent service disruptions.

### Enable Intune to integrate with Jamf Pro

1. In the Microsoft Azure portal, open **Microsoft Intune** > **Device Compliance** > **Compliance Connector for Jamf**.
2. Enable the Compliance Connector for Jamf by pasting the Application ID into the **Jamf Azure Active Directory App ID** field.
3. Click **Save**.

### Configure conditional access in Jamf Pro

1. In Jamf Pro, navigate to **Global Management** > **Conditional Access**. Click the **Edit** button on the
**Microsoft** tab.
2. Select the checkbox for **Enable Conditional Access with Microsoft**.
3. Provide the required information about your Azure tenant, including **Location**, **Domain name**, and the **Application ID** and **Application Key** you saved from the previous steps.
4. Click **Save**. Jamf Pro will test your settings and verify your success.
