---
# required metadata

title: Common Windows PC management tasks | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Common Windows PC management tasks with the Microsoft Intune computer client
Review the tasks in this topic to learn how to manage your computers that run the Intune client. If you have not yet installed the client on your computers, see [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Use policies to simplify PC management
### Manage the Windows Firewall
Policies simplify the administration of Windows Firewall settings on managed computers. For details, see [Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Manage the Microsoft Intune Center
The Microsoft Intune Center lets users:

-   Get applications from the company portal.

-   Check for updates.

-   Manage Microsoft Intune Endpoint Protection.

-   Request remote assistance.

The Microsoft Intune Center is installed on all managed computers. You can configure the following settings in an Intune policy and these are displayed to users in the Microsoft Intune Center:

|Policy setting|Details|
|------------------|--------------------|
|**Name**|The name of the administrator who manages the computer.<br /><br />Maximum length: 40 characters|
|**Phone number**|The telephone number of the administrator who manages the computer.<br /><br />Maximum length: 20 characters|
|**Email address**|The email address of the administrator who manages the computer.<br /><br />Maximum length: 40 characters|
|**Web site name**|The name of your support website for users.<br /><br />Maximum length: 40 characters|
|**Web site URL**|The URL of your support website.<br /><br />Maximum length: 150 characters|
|**Notes**|A note that is displayed to users.<br /><br />Maximum length: 120 characters|

### Manage software updates settings
Use policies to configure the settings that managed computers use to check for, and download software updates from Microsoft and from third-parties. For more information, see [Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Manage Endpoint Protection settings
Use policies to configure settings for Endpoint Protection that you then deploy to managed computers. This includes scan schedules, actions to take when malware is detected, and more. For more information, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## View hardware and software inventory
Intune collects detailed information about the hardware and software of managed computers. Use the information in the following procedures to learn how to create:

-   A report that lists information about the hardware capabilities of your computers.

-   A report that lists the software installed on each computer.

-   How to refresh a computers inventory to ensure that the data in the report is current.

### To display information about your computers

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Computer Inventory Reports**.

2.  On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report. For example, you could select that only computers that run Windows 8.1 will be displayed in the report.

3.  Choose **View Report** to open the **Computer Inventory Report** in a new window.

    You can sort the report by any of the columns, like **Name**, **Chassis Type** or **Manufacturer** by selecting each column heading.

### To display software installed on your computers

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Detected Software Reports**.

2.  On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report. For example, you could select that only software published by Microsoft will be displayed in the report.

3.  Choose **View Report** to open the **Detected Software Report** in a new window.

    You can sort the report by any of the columns, like **Name**, **Publisher** or **Category** by selecting each column heading. You can expand the updates in the list to show more detail (such as the computers on which it is installed) by clicking the directional arrow next to the list item.

### To refresh computer inventory to ensure it is current

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer for which you want to refresh inventory).

2.  Select a computer, or press and hold **Ctrl** to select multiple computers.

3.  On the taskbar, choose **Remote Tasks** &gt; **Refresh Inventory**.

4.  To view the task status, choose **Remote Tasks** in the bottom right corner of the page.

    The **Task Status** dialog box displays showing current remote tasks, task status, device name, and any reported errors, and provides a link to troubleshooting information.


## Remotely restart a Windows PC

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer you want to restart).

2.  Select one or more computers, and then choose **Remote Tasks** &gt; **Restart Computer**.

3.  To view the task status, choose **Remote Tasks** in the bottom right corner of the page.

4.  In the **Task Status** dialog box, review the current remote tasks, task status, device name, and any reported errors.

## Retire a computer

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer you want to retire).

2.  Select the devices you want to retire, and then choose **Retire/Wipe**.

To re-enroll a computer into Intune, reinstall the client software on the computer using the information in the [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) topic.

If a computer cannot connect to Intune, a message is displayed in the **Dashboard** workspace.

When you retire a computer:

-   It is removed from the Intune inventory, and the license associated with the computer is made available for re-use.

-   Its status no longer displays in the Intune console.

-   Intune removes the client software from the computer. If the computer is not connected to the Intune service, the client software will be removed next time it connects.

-   Microsoft Intune Endpoint Protection is removed from the computer. If the computer has another endpoint application installed and it is disabled, that application can be re-enabled after Microsoft Intune Endpoint Protection is removed to ensure that your computers are protected.

-   Any policies are removed from the computer and the values that were set by the policy will be changed.

-   The computer no longer receives software updates or malware definition updates from the Intune service.

-   Depending on how they are configured, retired computers can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.

    > [!IMPORTANT]
    > If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.

    If the client fails to uninstall, read [Troubleshoot Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) for more help.

## Manage user-device linking
Before you can deploy software to a user, you must link the user to a computer. You can link a user to multiple computers, but each computer can be linked to only one user. Users are automatically linked to any computers that they enroll in Intune by using the company portal.

### To link a user to a computer

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer you want to link to a user).

2.  Select the computer that you want to link a user, and then choose **Link User**.

    The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of computers to which each user is currently linked. If a user is already linked to the selected computer, that user’s name and user ID are displayed under **Current user**. If the computer is not linked to any user, **No User** appears under **Current User**.

3.  Do one of the following:

    -   To leave the computer linked to its current user, if there is one, choose **Cancel**.

    -   To remove the link to the current user, if there is one, choose **Remove link**&gt;**OK**.

    -   To link the computer to a new user, in the **All users** list, select a user. Confirm that the user data is correct, and then choose **OK**.

> [!TIP]
> If you want to restrict end users ability to link themselves to computers, enable the option **Restrict users' ability to link themselves to computers** in the **Microsoft Intune Agent Settings** policy.

## Respond to a Remote Assistance request
Users can request assistance by using Remote Assistance via Microsoft Easy Assist which is installed automatically on managed computers. When a request is made, an alert displays in the Intune console.

> [!IMPORTANT]
> Remote Assistance is not supported on computers running Windows 8 or later.
>
> If you accept a Remote Assistance request from a computer that does not have Microsoft Easy Assist installed, the user is prompted to install it. The computer must be restarted after the installation. Consider pre-loading Microsoft Easy Assist on your user’s computers to avoid this restart.

### To manage a Remote Assistance request

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Alerts** &gt; **Remote Assistance**.

2.  Select a Remote Assistance request in the **Alerts** list to open the properties page of the request.

3.  Choose **Approve request and launch Remote Assistance** to open a dialog box that provides options for resolving the alert.

4.  Do one of the following:

    -   **Accept the request** - To join the remote session, choose **Accept the Remote Assistance request**.

        The user sees the message: **Your request was accepted. Follow the instructions in Easy Assist to share a program or your desktop with your system administrator**.

        > [!IMPORTANT]
        > You cannot accept a remote assistance request on a Mac computer that is running the Intune administrator console.

    -   **Decline the request** - Close the **View Troubleshooting Information** window, and then choose **Close This Alert** in the alert properties window.

        The request is closed and the user sees a message stating that the request was declined. To request Remote Assistance again, the user must send a new Remote Assistance request. If you accidentally close a Remote Assistance alert, contact the user who sent the Remote Assistance request, and ask the user to send a new request.
