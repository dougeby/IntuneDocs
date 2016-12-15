---
# required metadata

title: Monitor MAM policies with Microsoft Intune | Microsoft Docs
description: See how many users have the policy, and drill down to find more details.
keywords:
author: andredm7ms.author: andredmmanager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Monitor mobile app management policies with Microsoft Intune
After you have set up a mobile app management (MAM) policy and applied it to users, you can monitor the compliance status in the [Azure portal](https://portal.azure.com). The Azure portal includes information about the users affected by the policy, the compliance status, and any issues that your users might be experiencing.
## Summary view
On the **Intune mobile application management** blade, you can see a summary of the compliance status:


![Summary tile on the Intune mobile application management blade](../media/mam-azure-portal-user-status-summary.png)

-   **Users**: The total number of users in your company who are using the apps that are associated with the policy.

-   **MANAGED BY POLICY**: The number of users who have used at least one of the apps in the work context.

-   **NO POLICY**: The number of users who are using the apps that are associated with the policy, but who are not targeted by the policy. You might consider adding these users to the policy.

- **Flagged users**: The number of users who are experiencing issues. Currently, only users with jailbroken devices are reported under **Flagged users**.


## Detailed view
You can get to the detailed view of the summary by choosing the **User status** tile and the **Flagged users** tile.

### User status
You can search for a single user and check the compliance status for that user. The **App reporting** blade shows the following information for a selected user:
- Devices that are associated with the user account

- Apps with a MAM policy on the device

- Status:

  - **Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.

  - **Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.

>[!NOTE]
> If the user you searched for does not have the MAM policy deployed to them, you will see a message informing you that the user is not targeted for any app policies.

To see the reporting for a user, follow these steps:

1.  To select a user, choose the **Summary** tile or choose the **APP REPORTING BY USER** option on the **Settings** blade:

    ![App reporting option on the Settings blade](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.

    ![Select user option on the App reporting blade](../media/mam-azure-portal-app-reporting-select-user.png)

3. Select the user from the list. You will see the details of the compliance status for that user.

    ![App reporting details](../media/mam-azure-portal-app-reporting-by-user.png)

### Flagged users
The detailed view shows the error message, the app that was accessed when the error happened, the platform of the device, and a time stamp.  

### See also
[Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [What to expect when your Android app is managed by MAM policies](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [What to expect when your iOS app is managed by MAM policies](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)
