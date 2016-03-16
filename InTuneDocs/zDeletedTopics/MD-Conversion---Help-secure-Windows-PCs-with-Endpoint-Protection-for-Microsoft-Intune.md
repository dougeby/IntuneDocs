---
title: MD Conversion - Help secure Windows PCs with Endpoint Protection for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5e755aee-0f43-410b-9d65-5989cf568e3e
---
# MD Conversion - Help secure Windows PCs with Endpoint Protection for Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] can help you to secure your managed computers in a number of ways, including Endpoint Protection which provides real-time protection against malware threats, keeps malware definitions up-to date, and automatically scans computers. [!INCLUDE[epshort](../Token/epshort_md.md)] also provides tools that help you to manage and monitor malware attacks

If you have not yet installed the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client on your computers, see [Install the Windows PC client with Microsoft Intune](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md).

Use the information in the following sections to help you configure, deploy and monitor [!INCLUDE[epshort](../Token/epshort_md.md)].

## Using Endpoint Protection in Microsoft Intune

### Before you start
As an IT admin, one of your top priorities is to keep the computers that you manage free of malware and viruses. Before you deploy [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] to client computers in your organization, you should decide how to protect your computers by selecting one of the following options and configuring its associated policy settings:

|I want to:|Endpoint Protection policy settings|More information|
|--------------|---------------------------------------|--------------------|
|Use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] only if no third-party endpoint protection application is installed<br /><br />You can use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] on all computers where a third-party endpoint protection application is not installed.|Install Endpoint Protection = **Yes**<br /><br />Enable Endpoint Protection = **Yes**<br /><br />Install Endpoint Protection even if a third-party endpoint protection application is installed = **No**|If a third-party endpoint protection application is detected, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] will not be installed, or will be uninstalled if it has already been installed.|
|Use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)], even if a third-party endpoint protection application is installed<br /><br />With this approach, you will be running [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] and the third party endpoint protection application (if it is installed) simultaneously. This is not a recommended configuration because of potential performance issues.|Install Endpoint Protection = **Yes**<br /><br />Enable Endpoint Protection = **Yes**<br /><br />Install Endpoint Protection even if a third-party endpoint protection application is installed = **Yes**|Use when:<br /><br />You want to switch to using [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)].<br /><br />You deploy a new client that will use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)]<br /><br />You upgrade any client that will use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)].|
|Use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] without [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)]<br /><br />In this case, you won’t be using [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] to protect your computers from malware and viruses. Instead, you will rely on a third-party endpoint protection application.|Install Endpoint Protection = **No**|If you are not using a third-party endpoint protection application, this configuration is not recommended, as it could expose your organization’s computers to malware or other attacks.<br /><br />[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] is not installed, and it is uninstalled if it was installed previously.|
If you want to switch from your current endpoint protection application to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)], use the following steps which are explained in more detail later in this topic:

1.  Leave your current endpoint protection application running while you deploy the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software to those computers.

2.  Confirm that [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] is installed and is helping to secure client computers.

3.  Remove the third-party endpoint protection software by:

    Using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] software distribution to deploy a software removal tool that is provided by the manufacturer of the third-party endpoint protection application. For more information, see [Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md).

    Removing the third-party endpoint protection application manually.

[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will not uninstall third-party endpoint protection applications.

### <a name="BKMK_HowtoConf"></a>How to configure Microsoft Intune Endpoint Protection
Use the following procedure to help you configure [!INCLUDE[epshort](../Token/epshort_md.md)] for [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] can manage [!INCLUDE[epshort](../Token/epshort_md.md)] for Windows 10 Technical Preview. Certain policy settings are only available for Windows 10.

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Policy** &gt; **Add Policy**.

2.  Configure and deploy a **Microsoft Intune Agent Settings** policy for the [!INCLUDE[epshort](../Token/epshort_md.md)] settings. You can use recommended settings or customize the settings. If you need more information about how to create and deploy policies, see the [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md) topic.

    The tables after this procedure show the values you can configure in the policy and also the recommended values that will be used if you don’t customize the policy. You can find these settings in the **Endpoint Protection** section.

You can view the deployed [!INCLUDE[epshort](../Token/epshort_md.md)] policy on the **All Policies** page of the **Policy** workspace.

#### Endpoint Protection service settings

|Policy setting|More information|
|------------------|--------------------|
|**Install Endpoint Protection**|Set to **Yes** to install [!INCLUDE[epshort](../Token/epshort_md.md)] on managed computers. If a third-party endpoint protection application is detected during installation, [!INCLUDE[epshort](../Token/epshort_md.md)] will not be installed unless **Install Endpoint Protection even if a third party endpoint protection application is installed** is set to **Yes**.<br /><br />Intune [!INCLUDE[epshort](../Token/epshort_md.md)] is installed on managed computers by default. If you don’t want [!INCLUDE[epshort](../Token/epshort_md.md)] installed on your managed computers, you must explicitly set this policy to **No**. If [!INCLUDE[epshort](../Token/epshort_md.md)] was previously installed and the policy is updated to **No**, then the [!INCLUDE[epshort](../Token/epshort_md.md)] client will be uninstalled.<br /><br />Recommended value: **Yes**|
|**Install Endpoint Protection even if a third party endpoint protection application is installed**|Set to **Yes** to install [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] even if a third-party endpoint protection application is detected.<br /><br />Recommended value: **Yes**|
|**Enable Endpoint Protection**|Set to **Yes** to enable [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] on computers which have the [!INCLUDE[epshort](../Token/epshort_md.md)] client.<br /><br />If set to **No**, and [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] is installed, the [!INCLUDE[epshort](../Token/epshort_md.md)] client user interface is not displayed to users and all protection features are inactive.<br /><br />Recommended value: **Yes**|
|**Disable Client UI**|Set to **Yes** to hide the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] client user interface from users (requires a client computer restart to take effect).<br /><br />Recommended value: **No**|
|**Install Endpoint Protection even if a third party endpoint protection application is installed**|Set to **Yes** to force the installation of [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)], even if a third-party endpoint protection application is detected.<br /><br />Recommended value: **No**|
|**Create a system restore point before malware remediation**|Set to **Yes** to create a Windows System Restore Point before any malware remediation begins.<br /><br />Recommended value: **Yes**|
|**Track resolved malware (days)**|Lets [!INCLUDE[epshort](../Token/epshort_md.md)] track resolved malware for a specified time so that you can manually check previously infected computers.<br /><br />You can specify a value from 0 to 30 days.<br /><br />Recommended value: **7 days**|
If you have set the policy values for **Install Endpoint Protection** and **Enable Endpoint Protection** to **Yes**, and the policy value for  **Install Endpoint Protection even if a third party endpoint protection application is installed** to **No**, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] will detect that another endpoint protection application is installed and will be not be installed, or uninstalled if it is already present (however, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] does report about the health of the other endpoint protection application in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)]).

#### Real-time protection settings

|Policy setting|More information|
|------------------|--------------------|
|**Enable real-time protection**|Enables monitoring and scanning of all files and applications that are accessed. It also blocks any malicious files and applications before they can run on computers.<br /><br />Recommended value: **Yes**|
|**Scan all downloads**|Enables the scanning of all files and attachments that are downloaded from the Internet to computers.<br /><br />Recommended value: **Yes**|
|**Monitor file and program activity on computers**|Enables the monitoring of incoming files and outgoing files, and program activity on computers. With this setting, [!INCLUDE[epshort](../Token/epshort_md.md)] can monitor when files and programs start to run and alert you about any actions they perform or actions that are taken on them.<br /><br />Recommended value: **Yes**|
|**Files monitored**|If **Monitor file and program activity on computers** is enabled, this setting allows you to choose if only incoming, only outgoing, or all files are monitored.<br /><br />Recommended value: **Monitor all files**|
|**Enable behavior monitoring**|Allows [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] to check for certain patterns of suspicious activity on client computers.<br /><br />Recommended value: **Yes**|
|**Enable Network Inspection System**|Enables Network Inspection System (NIS) on client computers. NIS uses signatures of known vulnerabilities from the [Microsoft Malware Protection Center](http://go.microsoft.com/fwlink/?LinkId=234249) to help detect and block malicious network traffic.<br /><br />Recommended value: **Yes**|

#### Scan schedule settings

|Policy setting|More information|
|------------------|--------------------|
|**Schedule a daily quick scan**|Schedules a daily quick scan of both frequently used files and important system files on computers. This quick scan has a minimal effect on performance.<br /><br />Recommended value: **Yes**|
|**Run a quick scan if you have missed two consecutive scans**|Configures [!INCLUDE[epshort](../Token/epshort_md.md)] to automatically run a quick scan on computers if they miss two consecutive, scheduled quick scans.<br /><br />Recommended value: **Yes**|
|**Schedule a full scan**|Configures a full scan of all files and resources on the local hard disks of computers. This scan can take some time and can affect computer performance (depending on the number of files and resources scanned).<br /><br />Recommended value: **No**|
|**Run a full scan if you have missed two consecutive full scans**|Configures [!INCLUDE[epshort](../Token/epshort_md.md)] to automatically run a full scan on computers if they miss two consecutive, scheduled full scans.<br /><br />Recommend value: Not configured|

#### Scan options settings

|Policy setting|More information|
|------------------|--------------------|
|**Run a full scan after installation of Endpoint Protection**|Configures [!INCLUDE[epshort](../Token/epshort_md.md)] to automatically run a full system scan after it is installed on computers. This scan runs only when computers are idle to minimize the effect on user productivity.<br /><br />Recommended value: **Yes**|
|**Automatically run a full scan when needed to follow up malware removal**|Set to **Yes** to let [!INCLUDE[epshort](../Token/epshort_md.md)] automatically run a full system scan on computers after the removal of malware to help confirm that other files were not affected.<br /><br />Recommended value: **Yes**|
|**Start a scheduled scan only when the computer is idle**|Set to **Yes** to prevent scheduled scans from starting when computers are in use to prevent any loss of user productivity.<br /><br />Recommended value: **Yes**|
|**Check for the latest malware definitions before starting a scan**|Set to **Yes** to let [!INCLUDE[epshort](../Token/epshort_md.md)] automatically check for the latest malware definitions before it starts a scan on computers.<br /><br />Recommended value: **Yes**|
|**Scan archive files**|Set to **Yes** to configure [!INCLUDE[epshort](../Token/epshort_md.md)] to scan for malware in archive files (like .zip or .cab files) on computers.<br /><br />Recommended value: **No**|
|**Scan email messages**|Set to **Yes** to configure [!INCLUDE[epshort](../Token/epshort_md.md)] to scan incoming email messages when they arrive on computers.<br /><br />Recommended value: **Yes**|
|**Scan files opened from network shared folders**|Set to **Yes** to configure [!INCLUDE[epshort](../Token/epshort_md.md)] to scan files that are opened from shared folders on the network. These are typically files that are accessed by using a UNC path. Enabling this feature can cause problems for users who have read-only access because they cannot remove malware.<br /><br />Recommended value: **No**|
|**Scan mapped network drives**|Set to **Yes** to configure [!INCLUDE[epshort](../Token/epshort_md.md)] to scan files on mapped network drives. Enabling this feature can cause problems for users who have read-only access because they cannot remove malware.<br /><br />Recommended value: **No**|
|**Scan removable drives**|Set to **Yes** to configure [!INCLUDE[epshort](../Token/epshort_md.md)] to scan for malware and unwanted software in the contents of removable drives, like USB flash drives, when you run a full scan on computers.<br /><br />Recommended value: **Yes**|
|**Limit CPU usage during a scan**|Configures the maximum percentage of CPU usage that can be used during scheduled scans on computers. You can set this value from 1 to 100 percent.<br /><br />Recommended value: **50%**|

#### Default actions settings

|Policy setting|More information|
|------------------|--------------------|
|**Choose how Endpoint Protection acts on malware of the following alert levels**|Specifies the default action that [!INCLUDE[epshort](../Token/epshort_md.md)] takes when malware of various alert levels is detected.<br /><br />For each alert level, you can remove the malware, quarantine it, or take Microsoft’s recommended action.<br /><br />Recommended value: **Recommended action**|

#### Excluded files and folders settings

|Policy setting|More information|
|------------------|--------------------|
|**Files and folders to exclude when running a scan or using real-time protection**|Excludes specific files or folders when a scan is run or when real-time protection is used on computers.|

#### Excluded processes settings

|Policy setting|More information|
|------------------|--------------------|
|**Processes to exclude when running a scan or using real-time protection**|Lets you exclude specific processes when a scan is run or from real-time protection. You can exclude only files with the following extensions: **.exe**, **.com** or **.scr**.|

#### Excluded file types settings

|Policy setting|More information|
|------------------|--------------------|
|**File extensions to exclude when running a scan or using real-time protection**|Lets you exclude specific file name extensions when a scan is run or when real-time protection is used on computers.|

#### Microsoft Active Protection Service Settings
Microsoft Active Protection Service is an online community that helps you decide how to respond to potential threats. The community also helps stop the spread of new malware infections.

|Policy setting|More information|
|------------------|--------------------|
|**Join Microsoft Active Protection Service**|**Yes** automatically sends information about detected malware to the Microsoft Active Protection Service. Microsoft does not use any information collected to identify you or to contact you.<br /><br />Recommended value: **Yes**|
|**Membership level**|If you selected to join the Microsoft Active Protection Service, this setting lets you choose from one of the following membership levels:<br /><br />**Basic** - Sends basic information to Microsoft about detected malware. This includes where the software came from, the actions that you apply or that [!INCLUDE[epshort](../Token/epshort_md.md)] applies automatically, and whether the actions were successful.<br /><br />**Advanced** - Sends more information to Microsoft about malware, spyware, and potentially unwanted software. This includes the location of the software, file names, how the software operates, and how it has affected your computer.<br /><br />Recommended value: **Advanced**|
|**Receive dynamic definitions based on Microsoft Active Protection Service reports**|**Yes** lets computers receive dynamic malware definitions based on information that [!INCLUDE[epshort](../Token/epshort_md.md)] sends to the Microsoft Active Protection Service (if you have joined it) about detected malware.<br /><br />Recommended value: **Yes**|

### Management tasks for Endpoint Protection
The following tasks help you to carry out various management tasks on managed computers that run [!INCLUDE[epshort](../Token/epshort_md.md)].

|I want to|From the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] console|From the managed computer|
|-------------|--------------------------------------------------------------------------|-----------------------------|
|Update malware definitions|From the **Groups** workspace, select the computers you want to update.<br /><br />Click **Remote Tasks** &gt; **Update Malware Definitions**.|Start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the Windows notification area.<br /><br />Click the **Update** tab, and then click **Update**.|
|Run a malware scan|From the **Groups** workspace, select the computers you want to scan.<br /><br />Click **Run a Full Malware Scan** or **Run a Quick Malware Scan**.|Start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the Windows notification area.<br /><br />Select **Quick**, **Full**, or **Custom**, and then click **Scan now**.|
You can view the status of a remote task by clicking the **Remote Tasks** link in the bottom right corner of the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

The **Remote Task Status** dialog box lists current remote tasks, task status, device name, any reported errors, and provides a link to troubleshooting information, if appropriate.

### <a name="BKMK_SCEPmon"></a>How to monitor Endpoint Protection
You monitor the status of malware on your computers by using the **Protection** workspace of the [Microsoft Intune administration console](https://manage.microsoft.com/). This workspace contains two pages:

|Page name|More information|
|-------------|--------------------|
|**Endpoint Protection Overview**|Displays important issues as links that you can click for more information. Issues that might be displayed include:<br /><br />**Malware instances that need follow-up** – Click the link to see a list of malware issues including the follow up action that needs to be taken to resolve the issue. You can further drill into this list to see which computers are affected.<br /><br />**Computers with malware that need follow-up** – Click the link to see all computers with unresolved malware issues including the follow up action that needs to be taken to resolve the issue.<br /><br />**Devices that are not protected** – Click the link to see computers that are not protected by any endpoint protection software, either because no software is installed, or because there is an error. Select a computer to view more details.<br /><br />**Devices with another endpoint protection application running** – Click the link to see computers that are running a third-party endpoint protection application.|
|**All Malware**|Displays a list of all active malware found on your computers. You can drill into this list to see all computers that are affected by a particular piece of malware, or you can select one of the following tasks:<br /><br />**View Properties** – Opens a page with more information about the selected malware.<br /><br />**Learn About This Malware** – Opens a topic from the Microsoft Malware Protection Center with more information about the malware.|
> [!IMPORTANT]
> The **Protection** workspace is not displayed in the administrator console until you have installed the client on, and are successfully managing at least one computer client.

### How to view Recent Detection Paths for malware on computers
Intune can display the paths of up to 10 most recently detected instances of malware on a device. The **Recent Detection Path** is disabled by default. To enable this view:

##### How to enable Recent Detection Paths for malware

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/) go **Groups** &gt; **All Devices** . **Malware**.

2.  Right-click a column header. A list of available columns appears.

3.  Mark the **Recent Detection Paths** checkbox in the list. The **Recent Detection Paths** column appears and displays up to 10 most recent malware instances monitored on the device.

## Need more help?
For further help and support, see [Troubleshoot Endpoint Protection in Microsoft Intune](../Topic/Troubleshoot-Endpoint-Protection-in-Microsoft-Intune.md).

## See Also
[Manage Windows PCs with Microsoft Intune](../Topic/Manage-Windows-PCs-with-Microsoft-Intune.md)

