---
title: Microsoft Intune reports
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
author: Nbigman
---
# Microsoft Intune reports
Use the information in this topic to help you create and manage [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] reports that provide information about software, hardware, and software licenses in your organization.

## Using Reports
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] reports provide information about software, hardware, and software licenses in your organization. Reports can help you confirm current needs and forecast future spending. The **Reports** workspace gives you the tools to create and manage reports. 

### Report types

|Report type|Description|
|---------------|---------------|
|**Update reports**|Show the software updates that succeeded on computers in your organization, in addition to the updates that failed, are pending, or are needed. For more information on software updates, see [Keep Windows PCs up to date with software updates in Microsoft Intune](../Topic/Keep-Windows-PCs-up-to-date-with-software-updates-in-Microsoft-Intune.md).|
|**Detected Software reports**|Show software installed on computers in your organization and includes the software versions. You can filter the information that displays based on the software publisher and the software category. You can expand the updates in the list to show more detail (such as the computers on which it is installed) by clicking the directional arrow next to the list item.<br /><br />When you retire computers or change their group memberships in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], it can take several minutes for these changes to be reflected in the detected software report. For the most accurate software inventory data, wait a few minutes after retiring computers or changing their group memberships before you run a detected software report that includes those computers.|
|**Computer Inventory reports**|Show information about managed computers in your organization. Use this report to plan hardware purchases and to understand more about the hardware needs of users in your organization. For more information on working with managed computers, see [Manage Windows PCs with Microsoft Intune](../Topic/Manage-Windows-PCs-with-Microsoft-Intune.md).|
|**Mobile Device Inventory reports**|Show information about the mobile devices in your organization. You can filter the information that displays based on groups, whether the device is a jailbroken or rooted device, and by operating system.|
|**License Purchase reports**|Show the software titles for all licensed software in selected license groups, based on their licensing agreements. If software license information has not refreshed in more than 24 hours, it will refresh when you generate a license report. A license report is not an exact calculation of software titles that are being used, or proof of compliance with agreements. The report is a tool to help you make licensing decisions for your organization. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] might not detect some products that are able to have a Microsoft volume license. The available filters are:<br /><br />**All agreements** shows all licensed software products that are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].<br /><br />**Volume licensing agreements** shows only VLSC software products.<br /><br />**Other software licensing agreements** shows software products that are managed outside VLSC.|
|**License installation reports**|Compare installed software on computers in your organization with your current license agreement coverage according to the  Volume Licensing Service Center (VLSC). Filters include:<br /><br />**All agreements** shows all licensed software products that are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].<br /><br />**Volume licensing agreements** shows only VLSC software products.<br /><br />**Other software licensing agreements** shows software products that are managed outside VLSC.|
|**Terms and Conditions reports**|Shows whether users accepted terms and conditions you deployed, and which version they accepted. You can specify up to 10 users whose acceptance of any terms and conditions that were deployed to them are shown, or show the acceptance status for a particular term deployed to them.|
|**Noncompliant Apps reports**|Show information about the users who have apps installed that are on your lists of compliant and noncompliant apps. Use this report to find users and devices that are not in compliance with your company app policies.|
|**Certificate Compliance reports**|Shows which certificates have been issued to users and devices through the Network Device Enrollment Service. Use this report to find certificates that are issued, expired, and revoked.|
|**Device History reports**|Shows a historical log of retire, wipe, and delete actions. Use this report to see who initiated actions on devices in the past.|
|**Mac OS X Hardware Report**|Displays hardware details for all enrolled Mac OS X devices in the groups you select. For information about the hardware inventory collected from these devices, see [Understand your devices with inventory in Microsoft Intune](../Topic/Understand-your-devices-with-inventory-in-Microsoft-Intune.md).|
|**Mac OS X Software Report**|Displays the software installed on all Mac OS X devices in the groups you selected. The report lists the software name (as a bundle ID), the short version (or friendly) name, the version, and the number of devices with the software installed.|

#### To create a report

1.  In the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], click **Reports**, and then click the report type you want to generate, described on the table above.

2.  On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report. For example, you could select that only software published by Microsoft will be displayed in the detected software report.

3.  Click **View Report** to open the report in a new window.

To sort the report by any of the displayed columns, click the column heading. Additionally, some reports allow you to expand items in the list to show more detail.

## More report actions
In addition, reports support the following actions:

|Action|More information|
|----------|--------------------|
|**Print**|In an open report, click the print icon and follow the instructions.|
|**Export**|In an open report, click the export icon and follow the instructions. You can export a report to comma separated values (.csv) or HTML format.|
|**Save**|On the **Create New Report** page, each user can save up to 100 reports. Configure the report parameters to your requirements and then click **Save**, or **Save As** if you want to use a different name.|
|**Load**|On the **Create New Report** page, click **Load** to retrieve any previously saved sets of report parameters.|
|**Delete**|In the **Reports** workspace, select the desired report type, click **Load**, and then, in the list of reports, click the delete (x) icon next to the report.|

## See Also
[Monitoring and reports with Microsoft Intune](../Topic/Monitoring-and-reports-with-Microsoft-Intune.md)

