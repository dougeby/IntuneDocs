---
# required metadata

title: Integrate Jamf Pro with Microsoft Intune for compliance | Microsoft Intune
description: Use Microsoft Intune compliance policies with Azure Active Directory conditional access to help secure Jamf-managed devices.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6

# optional metadata

#ROBOTS: 
#audience:
#ms.devlang:
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Integrate Jamf Pro with Intune for compliance

Applies to: Intune in the Azure portal

If your organization uses [Jamf Pro](https://www.jamf.com) to manage your end-users Macs, you can use Microsoft Intune compliance policies with Azure Active Directory conditional access to ensure that devices in your organization are compliant.

## Prerequisites

You need the following to configure conditional access with Jamf Pro:

- Jamf Pro 10.1.0 or later
- [Company Portal app for macOS](https://aka.ms/macoscompanyportal)
- macOS devices with OS X 10.11 Yosemite or later

## Connecting Intune to Jamf Pro

To connect Intune with Jamf Pro you:

1. Create a new application in Azure
2. Enable Intune to integrate with Jamf Pro
3. Configure conditional access in Jamf Pro

## Create an application in Azure Active Directory

1. In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory** > **App Registrations**.
2. Select **+New application registration**.
3. Enter a **display name**, such as **Jamf Conditional Access**.
4. Select **Web app / API**.
5. Specify the **Sign-On URL** using your Jamf Pro instance URL.
6. Select **Create**. The application is created and the portal presents the application details.
7. Save a copy of the **Application ID** for the new application. You specify this ID in a later procedure. Next, select **Settings** and go to **API Access** > **Keys**.
8. On the *Keys* pane, specify a **Description**, how long to wait before it **Expires**, and then select **Save** to generate the Application Key (Value).

   > [!IMPORTANT]
   > The Application Key is only shown once during this process. Be sure to save it somewhere where you can easily retrieve it.

8. On the *Settings* pane for the app, navigate to **API Access** > **Required Permissions**. Select any existing permissions and then click **Delete** and delete all permissions. Deleting existing permissions is necessary as you add a new permission, and the application only works if it has the single required permission.  
9. To assign a new permission, select **+Add** > **Select an API** > **Microsoft Intune API**, and then click **Select**.
10. On the *Enable Access* pane, select **Send device attributes to Microsoft Intune** and then click **Select**, and then **Done**.
11. On the *Required permissions* pane, select **Grant Permissions** and then **Yes** to apply the required permissions to the application.

    > [!NOTE]
    > If the Application Key expires, you must create a new Application Key in Microsoft Azure and then update the Conditional Access data in Jamf Pro. Azure allows you to have both the old key and new key active to prevent service disruptions.

## Enable Intune to integrate with Jamf Pro

1. In the [Azure portal](https://portal.azure.com), go to **Microsoft Intune** > **Device Compliance** > **Partner device management**.
2. Enable the Compliance Connector for Jamf by pasting the Application ID you saved during the previous procedure into the **Jamf Azure Active Directory App ID** field.
3. Select **Save**.

## Configure Microsoft Intune Integration in Jamf Pro

1. In Jamf Pro, navigate to **Global Management** > **Conditional Access**. Click the **Edit** button on the
**Microsoft Intune Integration** tab.
2. Select the checkbox for **Enable Microsoft Intune Integration**.
3. Provide the required information about your Azure tenant, including **Location**, **Domain name**, and the **Application ID** and **Application Key** you saved from the previous steps.
4. Select **Save**. Jamf Pro tests your settings and verify your success.

## Set up compliance policies and register devices

After you configure integration between Intune and Jamf, you need to [apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md).



## Next steps

- [Apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md)
- [Data Jamf sends to Intune](data-jamf-sends-to-intune.md)
