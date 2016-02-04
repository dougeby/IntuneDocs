---
title: robstack - V2 of Deploy apps to computers
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6059f907-2f74-45b8-a415-302b24160b10
author: robstackmsft
---
# robstack - V2 of Deploy apps to computers
Now that you've [learned the basics](https://technet.microsoft.com/library/dn646955.aspx) about [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] app deployment, in this topic, you'll learn how to actually configure and deploy apps to Windows PCs you manage. This generally involves three steps:

-   [Configure the app](#BKMK_Conf)

-   [Deploy the app](#BKMK_Depl)

-   [Monitor the app](#BKMK_Monitor)

For information about how to update and retire apps, see [Update apps using Microsoft Intune](../Topic/Update-apps-using-Microsoft-Intune.md).

> [!IMPORTANT]
> The information in this topic helps you to deploy apps to [Windows PCs that you manage using the client software](https://technet.microsoft.com/library/dn646959.aspx). If you want to deploy apps to [enrolled Windows PCs](https://technet.microsoft.com/library/mt346003.aspx) and other mobile devices, see [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md).

## <a name="BKMK_Conf"></a>Configure the app
In this procedure, you'll use the Intune Software Publisher to configure the properties of the app and upload it to your cloud storage space.

#### To configure an app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Apps** &gt; **Add Apps** to start the Intune software publisher.

    > [!TIP]
    > You might need to enter your Intune username and password before the publisher starts.

2.  On the **Software setup** page of the software publisher, configure the following:

    **Select how this software is made available to devices** - Choose **Software installer**, then specify:

    |Setting|Details|
    |-----------|-----------|
    |**Select the software installer file type**|This indicates the type of software you want to deploy. For a Windows PC, choose **Windows Installer**.|
    |**Specify the location of the software setup files**|Enter the location of the installation files or click **Browse** to select the location from a list.|
    |**Include additional files and subfolders from the same folder**|Some software that uses Windows Installer requires supporting files which are typically found in the same folder as the installation files. Select this option if you also want to deploy these supporting files.|
    This installation type uses some of your cloud storage space.

3.  On the **Software description** page, configure the following:

    > [!TIP]
    > Depending on the installer file you are using, some of these values might have been automatically entered, or might not appear.

    |Setting|Details|
    |-----------|-----------|
    |**Publisher**|Enter the name of the publisher of the app.|
    |**Name**|Enter the name of the app as it will be displayed in the company portal. **Tip:** Make sure all app names you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.|
    |**Description**|Enter a description for the app. This will be displayed to users in the company portal.|
    |**URL for software information**|(optional) Enter a URL to a website that contains information about this app. The URL will be displayed to users in the company portal.|
    |**Privacy URL**|(optional) Enter a URL to a website that contains privacy information for this app. The URL will be displayed to users in the company portal.|
    |**Category**|(optional) Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.|
    |**Icon**|(optional) Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.|

4.  On the **Requirements** page, select the requirements that must be met before the app can start to install on a device from:

    -   **Architecture** - Select whether this app can be installed on 32-bit, 64-bit, or both operating systems.

    -   **Operating System** - Select the minimum operating system on which this app can be installed.

5.  For the **Windows Installer** file type only (exe only): On the **Detection rules** page, you can configure rules to detect if the app you are configuring is already installed on a PC, or  you can use the default detection rules to automatically overwrite any previously installed versions of the app. The rules you can configure are:

    -   **File exists** - Specify the path to the file you want to detect. You can search under **%ProgramFiles%** (which searches **Program Files**\*&lt;path&gt;* and **Program Files (x86)**\*&lt;path&gt;*) on the PC or **%SystemDrive%** (which searches from the root drive of the PC, typically C:)

        .

    -   **MSI product code exists** - Click **Browse** to choose the Windows Installer (msi) file you want to detect.

    -   **Registry key exists** - Specify a registry key that begins with **HKEY_LOCAL_MACHINE\**. Both 32-bit and 64-bit registry paths are searched. If the key you specified exists in either location, the detection rule is satisfied.

    If the app satisfies any of the rules you have configured, it will not be installed.

6.  For the **Windows Installer** file type only (msi and exe): On the **Command line arguments** page, choose whether you want to supply optional command-line arguments for the installer. For example, some installers might support the argument **/q** to install silently with no user intervention.

7.  For the **Windows Installer** file type only (exe only): On the **Return codes** page, you can add new error codes that are interpreted by Intune when the app installs on a managed Windows PC.

    By default, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] uses industry-standard return codes to report the failure or success of an app package installation:

    -   **0** - Success

    -   **3010** - Success with restart

    You can also add your own return codes to this list. If you specify a list of return codes and the app installation returns a code that isn't on the list, it is interpreted as a failure.

8.  On the **Summary** page, review the information you specified. Once you are ready, click **Upload**.

9. Click **Close** to finish.

The app is displayed on the **Apps** node of the **Apps** workspace.

## <a name="BKMK_Depl"></a>Deploy the app
In this procedure, you'll deploy the app to selected devices or users.

#### To deploy the app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Apps** &gt; **Apps** to view the list of apps you manage.

2.  Select the app you want to deploy, and then click **Manage Deployment**.

3.  In the *&lt;app name&gt;* dialog box, first, on the **Select Groups** page, choose the user or device groups to which you want to deploy the app.

4.  On the **Deployment Action** page, configure the following:

    |Setting|Details|
    |-----------|-----------|
    |**Approval**|Choose whether the deployment is:<br /><br />-   **Required** (mandatory install)<br />-   **Available** (users install from the company portal on demand)<br />-   **Not Applicable** (the app is not installed or shown in the company portal)<br />-   **Uninstall** (the app will be uninstalled from targeted devices)|
    |**Deadline**|For required installations, choose how soon the app will be deployed. You can choose from the predefined values, or select **Custom** to configure your own deadline.|

## <a name="BKMK_Monitor"></a>Monitor the app
You can see the apps you manage, and their deployment status in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.

### To view the apps you manage and their status
In the **Apps** workspace, click the **Apps** node.

The list of apps you manage will be displayed. You can click on any app to see an installation status in the lower pane of the console windows. Click on this status to see further details. For example, if the status shows **1 user has this software available**, you can click the message to see the name of the user.

> [!TIP]
> You can use the **Filters** drop-down list to show only apps that meet the criteria you specify, like apps that failed to install, or apps that were successfully deployed.
> 
> ![](../Image/App-filters.JPG)

Additionally, the **Dashboard** workspace shows an overview of the status of your apps. If you click anywhere in the overview, you'll be taken to the list of apps.

### To view more detailed information about an app
In the list of apps, select any app, and then click **View Properties**.

On the **Software Properties** page for the app, click one of these tabs:

-   **General** - Shows general information about the app and it's installation status.

-   **Devices** - Shows the devices that successfully installed a targeted deployment of the app.

-   **Users** - Shows the users who's devices successfully installed a targeted deployment of the app.

As before, you can use the **Filters** drop-down list to configure the values shown on each of the tabs.

## See Also
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md)

