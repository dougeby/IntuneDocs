---
title: Install the Windows PC client with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
author: robstackmsft
---
# Install the Windows PC client with Microsoft Intune
Use this guide to help you get your computers managed by [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

## <a name="BKMK_Before"></a>Before you start
Before you start installing the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software, read the topic [Resolve GPO and Microsoft Intune policy conflicts](../Topic/Resolve-GPO-and-Microsoft-Intune-policy-conflicts.md) to understand what must be in place to install the client correctly and then return to these instructions.

## Get the client installed
Use these steps get the client installed:

-   [To download the client software](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md#BKMK_DL)

Then use one or more of the following methods to get the client installed:

-   [To manually deploy the client software](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md#BKMK_Manual)

-   [To automatically deploy the client software by using Group Policy](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md#BKMK_GP)

-   [How users can self-enroll their computers](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md#BKMK_Allow)

-   [Install the Microsoft Intune client software as part of an image](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md#BKMK_Image)

If you no longer need to manage a computer with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you can retire the computer, which also removes the client software from the computer. For more information, see [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md).

### <a name="BKMK_DL"></a>To download the client software

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Client Software Download**

2.  On the **Client Software Download** page, click **Download Client Software** and save the **Microsoft_Intune_Setup.zip** package containing the software to a secure location on your network.

    > [!NOTE]
    > The [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] client software installation package contains information about your account. If unauthorized users gain access to the installation package, they can enroll computers to the account that is represented by its embedded certificate.

3.  Extract the contents of the installation package to the secure location on your network.

    > [!IMPORTANT]
    > Do not rename or remove the **ACCOUNTCERT** file that is extracted or the client software installation will fail.

### <a name="BKMK_Manual"></a>To manually deploy the client software

1.  On a computer, browse to the folder where the client software installation files are located, and then run **Microsoft_Intune_Setup.exe** to install the client software.

    > [!NOTE]
    > The status of the installation is displayed when you hover over the icon in the taskbar on the client computer.

### <a name="BKMK_GP"></a>To automatically deploy the client software by using Group Policy

1.  In the folder that contains the files **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, run the following command to extract the Windows Installer-based installation programs for 32-bit and 64-bit computers:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Copy the **Microsoft_Intune_x86.msi** file, the **Microsoft_Intune_x64.msi** file, and the **MicrosoftIntune.accountcert** file to a network location that can be accessed by all computers to which the client software is to be installed.

    > [!IMPORTANT]
    > Do not separate or rename the files or the client software installation will fail.

3.  Use Group Policy to deploy the software to computers on your network.

    For more information about how to use Group Policy to automatically deploy software, see your Windows Server documentation.

### <a name="BKMK_Allow"></a>How users can self-enroll their computers
Users can self-enroll each of their computers through the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] company portal. Each enrolled computer is linked to the user account that was used to install the client software.

> [!NOTE]
> -   The user must be an administrator on the computer to install the client software.
> -   Self-enrolling requires that Internet Explorer is installed on the client computer.
> -   Each time a user self-enrolls a computer, it uses an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] license.
> -   You must use a work or school acccount to self-enroll a computer. You cannot self-enroll a computer using a Microsoft account.
> -   If the client software is already installed on a computer, the end-user will receive an error.

##### To self-enroll a computer (information for end-users)

1.  Log on to the company portal from the computer that you want to enroll.

2.  Click **Add Device**.

3.  Click **Download Software** and then click **Run**.

4.  Click **Next** to start the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Setup Wizard.

5.  When the setup wizard has completed, click **Finish**.

### <a name="BKMK_Image"></a>Install the Microsoft Intune client software as part of an image
You can deploy the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software to computers as part of an operating system image by using the following example procedure as a basis:

1.  Copy the client installation files, **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert** to the **%Systemdrive%\Temp\Microsoft_Intune_Setup** folder on the reference computer.

2.  Create the **WindowsIntuneEnrollPending** registry entry by adding the following command to the **SetupComplete.cmd** script:

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  Add the following command to **setupcomplete.cmd** to run the enrollment package with the /PrepareEnroll command-line argument:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > The **SetupComplete.cmd** script enables Windows Setup to make modifications to the system before a user logs on. The **/PrepareEnroll** command-line argument prepares a targeted computer to be automatically enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] after Windows Setup finishes.

4.  Put **SetupComplete.cmd** in the **%Windir%\Setup\Scripts** folder on the reference computer.

5.  Capture an image of the reference computer and then deploy this to targeted computers.

When the targeted computer restarts at the completion of Windows Setup, the **WindowsIntuneEnrollPending** registry key is created. The enrollment package checks whether the computer is enrolled. If the computer is enrolled, no further action is taken. If the computer is not enrolled, the enrollment package creates a [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Automatic Enrollment Task.

When the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Automatic Enrollment Task runs at the next scheduled time, it checks the existence of the **WindowsIntuneEnrollPending** registry value, and it tries to enroll the targeted computer in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. If the enrollment fails for any reason, the enrollment is retried the next time the task runs. The retries continue for a period of one month.

The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Automatic Enrollment Task, the **WindowsIntuneEnrollPending** registry value, and the account certificate are deleted from the targeted computer when the enrollment is successful or after one month.

## <a name="BKMK_Monitor"></a>Monitor and validate successful client deployment
Use one of the following procedures to help you monitor and validate successful client deployment.

#### To verify the installation of the client software from the Microsoft Intune administrator console

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Computers**.

2.  Scroll down the list of computers to find managed computers that are communicating with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or to search for a specific managed computer by typing the computer name, or any part of the name, in the **Search devices** box.

3.  Examine the status of the computer in the bottom pane of the console, and resolve any errors.

#### To create a computer inventory report to display all enrolled computers

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Computer Inventory Reports**.

2.  On the **Create New Report** page, leave all fields as the default values (unless you want to apply filters), and click **View Report**.

3.  The **Computer Inventory Report** page opens in a new window that displays all computers that are successfully enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    > [!TIP]
    > Click any column heading in the report to sort the list by the contents of that column.

## Need more help?
For further help and support, see [Troubleshoot Endpoint Protection in Microsoft Intune](../Topic/Troubleshoot-Endpoint-Protection-in-Microsoft-Intune.md).

## See Also
[Manage Windows PCs with Microsoft Intune](../Topic/Manage-Windows-PCs-with-Microsoft-Intune.md)

