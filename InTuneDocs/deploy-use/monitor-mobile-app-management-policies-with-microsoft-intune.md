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
You can monitor the compliance status of the mobile app management (MAM) policies that you've applied to users at the Intune app protection blade on the [Azure portal](https://portal.azure.com). You'll be able to find information about the users affected by the MAM policies, its compliance status, and any issues that your users might be experiencing.

There are three different places to monitor the compliance status:

-   Summary view

-   Detailed view

-   Reporting view

## Summary view

Follow the three steps below to open the Summary view:

1. Go to the [Azure portal](https://portal.azure.com), and enter your credentials.
2. Choose **More Services**, and type "Intune".
3. Choose **Intune App Protection**.

On **Intune mobile application management** blade, you can see a summary of the compliance status:

![Summary tile on the Intune mobile application management blade](../media/mam-azure-portal-user-status-summary.png)

-   **Users**: The total number of users in your company who are using the apps that are associated with the policy.

-   **MANAGED BY POLICY**: The number of users who have used at least one of the apps in the work context.

-   **NO POLICY**: The number of users who are using the apps that are associated with the policy, but who are not targeted by the policy. You might consider adding these users to the policy.

- **Flagged users**: The number of users who are experiencing issues. Currently, only users with jailbroken devices are reported under **Flagged users**.


## Detailed view
You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.

### User status
You can search for a single user and check the compliance status for that user. The **App reporting** blade shows the following information for a selected user:
- Devices that are associated with the user account

- Apps with a MAM policy on the device

- Status:

  - **Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.

  - **Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.

>[!NOTE]
> If the users you searched for does not have the MAM policy deployed to them, you'll see a message informing you that the user is not targeted by any MAM policies.

To see the reporting for a user, follow these steps:

1.  To select a user, choose the **Summary** tile.

	![Screenshot 3](../media/MAM-reporting-6.png)

2. On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.

    ![Select user option on the App reporting blade](../media/MAM-reporting-2.png)

3. Select the user from the list. You will see the details of the compliance status for that user.

### Flagged users
The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.

## Reporting view

You can find the same reports from the Detailed view, and additional reports to help you with the MAM policy compliance status:

![Screenshot-4](../media/MAM-reporting-7.png)

-   **App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.

-   **App protection app report:** It provides two different app protection statuses that admins can select before generating the report. The statuses can be protected or unprotected.

	![Screenshot-1](../media/MAM-reporting-1.png)

    -   User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.

        -   It shows all apps targeted by MAM policies for each user, and break down the status of each app as checked in with MAM policies, or that was targeted with a MAM policy but the app was never checked in.
<br></br>
    -   User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis. This might happen according to the following reasons:

        -   These apps are either being used by a user or an app that is not currently targeted by a MAM policy.

        -   All apps are checked in, but aren't getting any MAM policies.

![Screenshot-2](../media/MAM-reporting-4.png)

## See also
[Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [What to expect when your Android app is managed by MAM policies](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [What to expect when your iOS app is managed by MAM policies](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)
