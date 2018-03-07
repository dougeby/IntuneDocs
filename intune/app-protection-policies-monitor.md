---
# required metadata

title: How to monitor app protection policies 
titleSuffix: Microsoft Intune
description: Monitor the compliance status of mobile app management policies in Intune.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to monitor app protection policies
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**If you are not in the Azure portal**, this topic explains [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in the Intune classic portal.


Monitor the compliance status of the mobile app management (MAM) policies that you've applied to users at the Intune app protection pane on the [Azure portal](https://portal.azure.com). Find information about the users affected by the MAM policies, its compliance status, and any issues that your users might be experiencing.

There are three different places to monitor the compliance status:

-   Summary view

-   Detailed view

-   Reporting view

## Summary view

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **Monitor** > **App protection status**, to see the summary view:

![Summary tile on the Intune mobile application management pane](./media/app-protection-user-status-summary.png)

-   **Users**: The total number of users in your company who are using an app which is associated with a policy in a work context.

-   **MANAGED BY POLICY**: The number of users who have used an app who have a policy assigned to them in a work context.

-   **NO POLICY**: The number of users who are using an app that is not targeted by any policy in a work context. You might consider adding these users to the policy.
	> [!NOTE]
	> If you have multiple policies per platform, a user is considered managed by policy when they have at least one policy assigned to them.

- **Flagged users**: The number of users who are experiencing issues. Currently, only users with jailbroken devices are reported under **Flagged users**.


## Detailed view
You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.

### User status
You can search for a single user and check the compliance status for that user. The **App reporting** pane shows the following information for a selected user:
- Devices that are associated with the user account

- Apps with a MAM policy on the device

- Status:

  - **Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.

  - **Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.

>[!NOTE]
> If the users you searched for do not have the MAM policy deployed to them, you see a message informing you that the user is not targeted by any MAM policies.

To see the reporting for a user, follow these steps:

1.  To select a user, choose the **Summary** tile.

	![Screenshot highlighting the Summary tile on the Intune mobile application management, Settings blade](./media/MAM-reporting-6.png)

2. On the **App reporting** pane that opens, choose **Select user** to search for an Azure Active Directory user.

    ![Screenshot highlighting the Select user option on the App reporting pane](./media/MAM-reporting-2.png)

3. Select the user from the list. You can see the details of the compliance status for that user.

### Flagged users
The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.

## Reporting view

You can find the same reports from the Detailed view, and additional reports to help you with the MAM policy compliance status:

![Screenshot highlighting 2 reports available in the Settings pane](./media/MAM-reporting-7.png)

-   **App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.

-   **App protection app report:** It provides two different app protection statuses that admins can select before generating the report. The statuses can be protected or unprotected.

    -   User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.

        -   It shows all apps targeted by MAM policies for each user, and break down the status of each app as checked in with MAM policies, or that was targeted with a MAM policy but the app was never checked in.
<br></br>
    -   User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis. This might happen according to the following reasons:

        -   These apps are either being used by a user or an app that is not currently targeted by a MAM policy.

        -   All apps are checked in, but aren't getting any MAM policies.

![Screenshot showing a user's App reporting blade with a table of details for 3 registered apps](./media/MAM-reporting-4.png)

## Table grouping

Once the **App protection user report** data shows up, you can aggregate data by the following:

- **Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.
- **App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.

## Export app protection activities to CSV

You can export all your app protection policy activities to a single .csv file. This can be helpful to analyze all the app protection statuses reported from the users.

Follow these steps to generate the App protection report:

1. On the Intune mobile application management pane, choose **App protection report**.

	![Screenshot highlighting the App protection download link on the Intune mobile application management pane](./media/app-protection-report-csv-2.png)

2. Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.

	![Screenshot of the Save report confirmation box](./media/app-protection-report-csv-1.png)

## See also
[Manage data transfer between iOS apps](data-transfer-between-apps-manage-ios.md)

* [What to expect when your Android app is managed by app protection policies](app-protection-enabled-apps-android.md)
* [What to expect when your iOS app is managed by app protection policies](app-protection-enabled-apps-ios.md)
