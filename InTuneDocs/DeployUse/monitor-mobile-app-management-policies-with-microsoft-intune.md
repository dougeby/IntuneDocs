---
title: Monitor mobile app management policies with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
author: karthikaraman
---
# Monitor mobile app management policies with Microsoft Intune
After you have configured a MAM policy and applied it to the users, you can monitor the compliance status on the Azure portal. The Azure portal includes information about the users affected by the policy, the compliance status for each app, and MAM policy related issues that your end users might be experiencing.
## Summary view
On the **Intune mobile application management** blade you can see a summary of the compliance status as described below:


![](../media/AppManagement/AzurePortal_MAM_MonitorUsers.png)

-   **USERS:** The total number of users in your company who are using the apps that are listed in your MAM policy.

-   **MANAGED BY POLICY:**- The number of users who have use at least one of the apps associated with the policy in the work context.

-   **NO POLICY:** The number of users who are using the apps listed in your policy, but are not targeted by your policy.  You may consider adding these users to your policy.

- **Flagged users:** The number of users experiencing issues. Currently only users with jailbroken devices are reported under **Flagged users**.


## Detailed view
You can get to the detailed views by clicking on the **User status** tile and the **Flagged users** tile.

### User status
You can search for a single user and look at the compliance status for that user. The **App reporting** blade displays the following information for a selected user:
- Device(s) that are associated with the user account
- App(s) with MAM policy on the device
- Status:

  **Checked in:** This means that the policy was deployed to the user, and app was used in work context and successfully received the policy.

  **Not checked in:** This means the policy was deployed to the user, but app has not been used in the work context since then.

To see the reporting for a user, follow these steps:

**Step 1:**  To select a user, click on the Summary tile or choose the **APP REPORTING BY USER** option in the **Settings** blade as shown below:

![App reporting option on the settings blade](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

**Step 2:** This opens the **App reporting** blade. Choose **Select user** to search for an Azure Active Directory user.

![select user option on the App reporting blade](../media/mam-azure-portal-app-reporting-select-user.png)

**Step 3:** After selecting the user from the list, you should see the details of the compliance status for that user.

![App reporting details](../media/mam-azure-portal-app-reporting-by-user.png)
### Flagged users
The detailed view displays the error message, the app that was accessed when the error happened, the platform of the device, and a time stamp.  
![](../media/AppManagement/AzurePortal_MAM_FlaggedUserDetails.png)

<!---##  Wipe requests
-   The **Wipe requests** tile shows you the summary report of the status of the wipe requests you made. Clicking on this tile will open a new blade that has more detailed information. For a detailed description of the wipe request information that is displayed in this blade, read the [Wipe managed company app data with Microsoft Intune](../Topic/Wipe-managed-company-app-data-with-Microsoft-Intune.md) topic.

    ![](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)--->

### See also
[Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

[End-user experience for MAM enabled app](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md)
