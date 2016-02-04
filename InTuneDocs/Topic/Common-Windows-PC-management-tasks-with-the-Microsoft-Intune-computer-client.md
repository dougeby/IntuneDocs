---
title: Common Windows PC management tasks with the Microsoft Intune computer client
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
author: robstackmsft
---
# Common Windows PC management tasks with the Microsoft Intune computer client
Review the information in this topic to learn how to manage your computers that run the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] client. If you have not yet installed the client on your computers, see [Install the Windows PC client with Microsoft Intune](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md).

## <a name="BKMK_PolicyTasks"></a>Tasks that use Microsoft Intune policies

### Use policies to manage the Windows Firewall
Policies simplify the administration of Windows Firewall settings on managed computers. For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).

### Use policies to manage the Microsoft Intune Center
The [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Center lets users:

-   Get applications from the company portal.

-   Check for updates.

-   Manage [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] [!INCLUDE[epshort](../Token/epshort_md.md)].

-   Request remote assistance.

The [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Center is installed on all managed computers. You can configure the following settings in a [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Center policy and these are displayed to users in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Center:

|Policy setting|More information|
|------------------|--------------------|
|**Name**|The name of the administrator who manages the computer.<br /><br />Maximum length: 40 characters|
|**Phone number**|The telephone number of the administrator who manages the computer.<br /><br />Maximum length: 20 characters|
|**Email address**|The email address of the administrator who manages the computer.<br /><br />Maximum length: 40 characters|
|**Web site name**|The name of your support website for users.<br /><br />Maximum length: 40 characters|
|**Web site URL**|The URL of your support website.<br /><br />Maximum length: 150 characters|
|**Notes**|A note that is displayed to users.<br /><br />Maximum length: 120 characters|

### Use policies to manage software updates settings
Use policies to configure the settings that managed computers use to check for, and download software updates from Microsoft and from third-parties. For more information, see [Keep Windows PCs up to date with software updates in Microsoft Intune](../Topic/Keep-Windows-PCs-up-to-date-with-software-updates-in-Microsoft-Intune.md).

### Use policies to manage Endpoint Protection settings
Use policies to configure settings for [!INCLUDE[epshort](../Token/epshort_md.md)] that you then deploy to managed computers. This includes scan schedules, actions to take when malware is detected, and more. For more information, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).

## <a name="BKMK_Inventory"></a>View hardware and software inventory
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] collects detailed information about the hardware and software of managed computers. Use the information in the following procedures to learn how to create:

-   A report that lists information about the hardware capabilities of your computers.

-   A report that lists the software installed on each computer.

-   How to refresh a computers inventory to ensure that the data in the report is current.

#### To display information about your computers

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Computer Inventory Reports**.

2.  On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report. For example, you could select that only computers that run Windows 8.1 will be displayed in the report.

3.  Click **View Report** to open the **Computer Inventory Report** in a new window.

    You can sort the report by any of the columns, like **Name**, **Chassis Type** or **Manufacturer** by clicking each column heading.

#### To display software installed on your computers

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Detected Software Reports**.

2.  On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report. For example, you could select that only software published by Microsoft will be displayed in the report.

3.  Click **View Report** to open the **Detected Software Report** in a new window.

    You can sort the report by any of the columns, like **Name**, **Publisher** or **Category** by clicking each column heading. You can expand the updates in the list to show more detail (such as the computers on which it is installed) by clicking the directional arrow next to the list item.

#### To refresh computer inventory to ensure it is current

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** (or another group that contains the computer for which you want to refresh inventory).

2.  Select a computer, or press and hold **Ctrl** to select multiple computers.

3.  On the taskbar, click **Remote Tasks** &gt; **Refresh Inventory**.

4.  To view the task status, click **Remote Tasks** in the bottom right corner of the page.

    The **Task Status** dialog box displays showing current remote tasks, task status, device name, and any reported errors, and provides a link to troubleshooting information.

## <a name="BKMK_Additional"></a>Additional tasks
In addition to policies, you can also perform the following management tasks on your computers:

#### To remotely restart a computer

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** (or another group that contains the computer you want to restart).

2.  Select one or more computers, and then click **Remote Tasks** &gt; **Restart Computer**.

3.  To view the task status, click **Remote Tasks** in the bottom right corner of the page.

4.  In the **Task Status** dialog box, review the current remote tasks, task status, device name, and any reported errors.

### <a name="BKMK_Retire"></a>To retire a computer

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** (or another group that contains the computer you want to retire).

2.  Select the devices you want to retire, and then click **Retire/Wipe**.

To re-enroll a computer into the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service, reinstall the client software on the computer using the information in the [Install the Windows PC client with Microsoft Intune](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md) topic.

If a computer cannot connect to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], a message is displayed in the **Dashboard** workspace.

When you retire a computer:

-   It is removed from the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] inventory, and the license associated with the computer is made available for re-use.

-   Its status no longer displays in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

-   [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] removes the client software from the computer. If the computer is not connected to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service, the client software will be removed next time it connects.

-   [!INCLUDE[epshort](../Token/epshort_md.md)] is removed from the computer. If the computer has another endpoint application installed and it is disabled, that application can be re-enabled after [!INCLUDE[epshort](../Token/epshort_md.md)] is removed to ensure that your computers are protected.

-   Any policies are removed from the computer and the values that were set by the policy will be changed.

-   The computer no longer receives software updates or malware definition updates from the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.

-   Depending on how they are configured, retired computers can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.

    > [!IMPORTANT]
    > If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.

    If the client fails to uninstall, read [Troubleshoot Endpoint Protection in Microsoft Intune](../Topic/Troubleshoot-Endpoint-Protection-in-Microsoft-Intune.md) for more help.

### <a name="BKMK_UserDeviceLinking"></a>How to manage user-device linking
Before you can deploy software to a user, you must link the user to a computer. You can link a user to multiple computers, but each computer can be linked to only one user. Users are automatically linked to any computers that they enroll in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] by using the company portal.

##### To link a user to a computer

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** (or another group that contains the computer you want to link to a user).

2.  Select the computer that you want to link a user, and then click **Link User**.

    The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of computers to which each user is currently linked. If a user is already linked to the selected computer, that user’s name and user ID are displayed under **Current user**. If the computer is not linked to any user, **No User** appears under **Current User**.

3.  Do one of the following:

    -   To leave the computer linked to its current user, if there is one, click **Cancel**.

    -   To remove the link to the current user, if there is one, click **Remove link**&gt;**OK**.

    -   To link the computer to a new user, in the **All users** list, select a user. Confirm that the user data is correct, and then click **OK**.

> [!TIP]
> If you want to restrict end users ability to link themselves to computers, enable the option **Restrict users' ability to link themselves to computers** in the **Microsoft Intune Agent Settings** policy.

### Respond to a Remote Assistance request
Users can request assistance by using Remote Assistance via Microsoft Easy Assist which is installed automatically on managed computers. When a request is made, an alert displays in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administrator console.

> [!IMPORTANT]
> Remote Assistance is not supported on computers running Windows 8 or later.
> 
> If you accept a Remote Assistance request from a computer that does not have Microsoft Easy Assist installed, the user is prompted to install it. The computer must be restarted after the installation. Consider pre-loading Microsoft Easy Assist on your user’s computers to avoid this restart.

##### To manage a Remote Assistance request

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Alerts** &gt; **Remote Assistance**.

2.  Select a Remote Assistance request in the **Alerts** list to open the properties page of the request.

3.  Click **Approve request and launch Remote Assistance** to open a dialog box that provides options for resolving the alert.

4.  Do one of the following:

    -   **Accept the request** - To join the remote session, click **Accept the Remote Assistance request**.

        The user sees the message: **Your request was accepted. Follow the instructions in Easy Assist to share a program or your desktop with your system administrator**.

        > [!IMPORTANT]
        > You cannot accept a remote assistance request on a Mac computer that is running the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

    -   **Decline the request** - Close the **View Troubleshooting Information** window, and then click **Close This Alert** in the alert properties window.

        The request is closed and the user sees a message stating that the request was declined. To request Remote Assistance again, the user must send a new Remote Assistance request. If you accidentally close a Remote Assistance alert, contact the user who sent the Remote Assistance request, and ask the user to send a new request.

## <a name="BKMK_Next"></a>Need more help?
For further help and support, see [Troubleshoot Endpoint Protection in Microsoft Intune](../Topic/Troubleshoot-Endpoint-Protection-in-Microsoft-Intune.md).

## See Also
[Manage Windows PCs with Microsoft Intune](../Topic/Manage-Windows-PCs-with-Microsoft-Intune.md)

