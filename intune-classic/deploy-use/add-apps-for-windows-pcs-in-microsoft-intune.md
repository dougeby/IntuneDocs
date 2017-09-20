---
# required metadata

title: Add apps for Windows PCs that run the Intune software client
description: Use the information in this topic to learn how to add apps for Windows PCs to Intune before you deploy them.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Add apps for Windows PCs that run the Intune software client

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use the information in this topic to learn how to add apps to Intune before you deploy them.

> [!IMPORTANT]
> The information in this topic helps you add apps for Windows PCs that you manage by using the Intune software client. If you want to add apps for enrolled Windows PCs and other mobile devices, see [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

To install apps to PCs, they must be capable of being installed silently, with no user interaction. If this is not the case, the installation will fail.


## Add the app
You use the Intune Software Publisher to configure the properties of the app and upload it to your cloud storage space by using the following procedure:

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher.

    > [!TIP]
    > You might need to enter your Intune user name and password before the publisher starts.

2.  On the **Software setup** page of the publisher, under **Select how this software is made available to devices**, choose **Software installer**, and then specify:

	- **Select the software installer file type**. This indicates the type of software that you want to deploy. For a Windows PC, choose **Windows Installer**.
    - **Specify the location of the software setup files**. Enter the location of the installation files, or choose **Browse** to select the location from a list.
    - **Include additional files and subfolders from the same folder**. Some software that uses Windows Installer requires supporting files. These must be located in the same folder as the installation file. Select this option if you also want to deploy these supporting files.

	For example, if you want to publish an app named Application.msi to Intune, the page would look like this:
	![Software setup page of the publisher](./media/publisher-for-pc.png)

   This installation type uses some of your cloud storage space.

3.  On the **Software description** page, configure the following.

    > [!NOTE]
    > Depending on the installer file that you are using, some of these values might have been automatically entered, or they might not appear.

	- **Publisher**. Enter the name of the publisher of the app.
    - **Name**. Enter the name of the app as it will be displayed in the company portal.<br />Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
    - **Description**. Enter a description for the app. This will be displayed to users in the company portal.
    - **URL for software information** (optional). Enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
    - **Privacy URL** (optional). Enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
    - **Category** (optional). Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
    - **Icon** (optional). Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.

4.  On the **Requirements** page, select the requirements that must be met before the app can be installed. Choose from:

    - **Architecture**. Select whether this app can be installed on 32-bit, 64-bit, or both operating systems.
    - **Operating System**. Select the minimum operating system on which this app can be installed.

5.  On the **Detection rules** page, you can configure rules to detect whether the app that you are configuring is already installed on a PC. Or,  you can use the default detection rules to automatically overwrite any previously installed versions of the app. This option is for Windows Installer (.exe files only).

	The rules that you can configure are:
	- **File exists**. Specify the path to the file that you want to detect. You can search under **%ProgramFiles%** (which searches **Program Files**\&lt;path&gt; and **Program Files (x86)**\&lt;path&gt;) on the PC or **%SystemDrive%** (which searches from the root drive of the PC, typically drive C).
	- **MSI product code exists**. Choose **Browse** to choose the Windows Installer (.msi) file that you want to detect.
	- **Registry key exists**. Specify a registry key that begins with **HKEY_LOCAL_MACHINE\**. Both 32-bit and 64-bit registry paths are searched. If the key that you specified exists in either location, the detection rule is satisfied.

    If the app satisfies any of the rules that you have configured, it will not be installed.

6.  For the **Windows Installer** file type only (.msi and .exe): On the **Command line arguments** page, choose whether you want to supply optional command-line arguments for the installer.
	The following parameters are added automatically by Intune:
	- For .exe files, **/install** is added.
	- For .msi files, **/quiet** is added.
	Note that these options will only work if the creator of the app package enabled functionality for this.

7.  For the **Windows Installer** file type only (.exe only): On the **Return codes** page, you can add new error codes that Intune interprets when the app is installed on a managed Windows PC.

    By default, Intune uses industry-standard return codes to report the failure or success of an app package installation: **0** (Success) or **3010** (Success with restart). You can also add your own return codes to this list. If you specify a list of return codes and the app installation returns a code that isn't on the list, it is interpreted as a failure.

8.  On the **Summary** page, review the information that you specified. When you are ready, choose **Upload**.

9. Choose **Close** to finish.

The app is displayed on the **Apps** node of the **Apps** workspace.

## Next steps

After you've created an app, the next step is to deploy it. To find out more, see [Deploy apps in Microsoft Intune](deploy-apps.md).

If you want to read more information about tips and tricks to deploy software to Windows PCs, see the blog post [Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/).
