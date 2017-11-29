---
# required metadata

title: Integrate Jamf Pro with Intune for compliance
titlesuffix: "Azure portal"
description: "Use compliance to help secure Jamf-managed devices."
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/28/2017
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

# Integrate Jamf Pro with Intune for compliance

|Applies to: Intune in the Azure portal |
|--|
|Looking for documentation about Intune in the classic portal? [Go here](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Currently in Private Preview|
|--|
|The features described in this topic are only available to customers currently in private preview. This message will be removed when it has been released for all customers.|
| |

If your organization uses [Jamf Pro](https://www.jamf.com) to manage your end users' Macs, you can use Microsoft Intune compliance policies with Azure Active Directory conditional access to ensure that devices in your organization are compliant.

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

## Create a new application in Azure Active Directory

1. Open **Azure Active Directory** > **App Registrations**.
2. Click **+New application registration**.
3. Enter a **display name**, such as **Jamf Conditional Access**.
4. Select **Web app / API**.
5. Specify the **Sign-On URL** using your Jamf Pro instance URL.
6. Click **Create application**.
7. Save the newly-created **Application ID**, then open **Settings** and navigate to **API Access** > **Keys** to create a new Application Key. Enter a **Description**, how long to wait before it **Expires**, then save the Application Key. 

  > [!IMPORTANT]
  > The Application Key is only shown once during this process. Be sure to save it somewhere where you can easily retrieve it.

8. Navigate to **All Settings** > **API Access** > **Required Permissions** and delete all permissions.

  > [!NOTE]
  > Add a new required permission. The application can have only work properly if it has the single required permission.

9.  Select **Microsoft Intune API** and click **Select**.
10. Choose **Send device attributes to Microsoft Intune** and click **Select**.
11. Click the **Grant Permissions** button after saving the required permissions for the application.

  > [!NOTE]
  > If the Application Key expires, you must create a new Application Key in Microsoft Azure and then update the Conditional Access data in Jamf Pro. Azure allows you to have both the old key and new key active to prevent service disruptions.

## Enable Intune to integrate with Jamf Pro

1. In the Microsoft Azure portal, open **Microsoft Intune** > **Device Compliance** > **Partner device management**.
2. Enable the Compliance Connector for Jamf by pasting the Application ID into the **Jamf Azure Active Directory App ID** field.
3. Click **Save**.

## Configure Microsoft Intune Integration in Jamf Pro

1. In Jamf Pro, navigate to **Global Management** > **Conditional Access**. Click the **Edit** button on the
**Microsoft Intune Integration** tab.
2. Select the checkbox for **Enable Microsoft Intune Integration**.
3. Provide the required information about your Azure tenant, including **Location**, **Domain name**, and the **Application ID** and **Application Key** you saved from the previous steps.
4. Click **Save**. Jamf Pro will test your settings and verify your success.

## Set up compliance policies and register devices

After you finish configuring integration between Intune and Jamf, you can [apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md).

## Information shared from Jamf Pro to Intune

Jamf Pro captures inventory information about managed macOS devices. Jamf Pro reports the following information to Intune:

* Device Azure AD ID
* JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)
* OS Version
* User Azure AD ID
* Encrypted (FileVault 2)
* Gatekeeper Status
* Password: minimum number of character sets
* Password expiration (days)
* Password Type - simple, alphanumeric, or unknown
* Prevent Auto Login
* Required Passcode Length
* Password: number of previous passwords to prevent reuse
* System Integrity Protection
* Last Check-In Time
* Architecture Type
* Available RAM Slots
* Battery Capacity
* Boot ROM
* Bus Speed
* Cache Size
* Device Name
* Domain Join
* Jamf ID
* MAC address
* Make
* Model
* Model Identifier
* NIC Speed
* Number of Cores
* Number of Processors
* OS
* Platform
* Processor Speed
* Processor Type
* Secondary MAC Address
* Serial Number
* SMC Version
* Total RAM
* UDID
* User Email

## Next steps

- [Apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md)
