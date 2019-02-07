---
# required metadata

title: Add PowerShell scripts to Windows 10 devices in Microsoft Intune - Azure | Microsoft Docs
description: Create and run PowerShell scripts, assign the script policy to Azure Active Directory groups, use reports to monitor the scripts, and see the steps to delete scripts you add on Windows 10 devices in Microsoft Intune. Also see some common issues and resolutions. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/05/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Use PowerShell scripts on Windows 10 devices in Intune

Use the Microsoft Intune management extension to upload PowerShell scripts in Intune to run on Windows 10 devices. The management extension enhances Windows 10 mobile device management (MDM), and makes it easier to move to modern management.

This feature applies to:

- Windows 10 and later

## Move to modern management

End-user computing is going through a digital transformation. Classic, traditional IT focuses on a single device platform, business-owned devices, users that work from the office, and different manual, reactive IT processes. The modern workplace uses many platforms that are user and business owned, allows users to work from anywhere, and provides automated and proactive IT processes.

MDM services, such as Microsoft Intune, can manage mobile and desktop devices running Windows 10. The built-in Windows 10 management client communicates with Intune to run enterprise management tasks. There are some tasks that you might need, such as advanced device configuration, troubleshooting, and legacy Win32 app management that's currently not available in Windows 10 MDM. For these capabilities, you can run the Intune software client on your Windows 10 devices. [Compare managing Windows PCs as computers or mobile devices](pc-management-comparison.md) is a great resource.

The Intune management extension supplements the in-box Windows 10 MDM features. You can create PowerShell scripts to run on the Windows 10 devices. For example, you can create a PowerShell script that installs a legacy Win32 app, uploads the script to Intune, assigns the script to an Azure Active Directory (AD) group, and runs the script. You can then monitor the run status of the script from start to finish.

## Prerequisites

The Intune management extension has the following prerequisites:

- Devices must be joined or registered to Azure AD and Azure AD is configured for [auto-enrollment into Intune](windows-enroll.md#enable-windows-10-automatic-enrollment). The Intune management extension supports Azure AD joined, hybrid domain joined, and co-managed enrolled Windows devices.
- Devices must run Windows 10 version 1607 or later.
- The Intune management extension agent is installed when a PowerShell script or a Win32 app is deployed to a user or device security group.

## Create a script policy 

1. In the [Azure portal](https://portal.azure.com), select **All services** > filter on **Intune** > select **Intune**.
2. Select **Device configuration** > **PowerShell scripts** > **Add**.
3. Enter the following properties:

    - **Name**: Enter a name for the PowerShell script. 
    - **Description**: Enter a description for the PowerShell script. This setting is optional, but recommended. 
    - **Script location**: Browse to the PowerShell script. The script must be less than 200 KB (ASCII).

4. Choose **Configure**, and enter the following properties:

    - **Run this script using the logged on credentials**: Select **Yes** to run the script with the user's credentials on the device. Choose **No** (default) to run the script in the system context. Select **Yes** unless the script is required to run in the system context.
    - **Enforce script signature check**: Select **Yes** if the script must be signed by a trusted publisher. Select **No** (default) if there isn't a requirement for the script to be signed. 
    - **Run script in 64-bit PowerShell host**: Select **Yes** to run the script in a 64-bit PowerShell (PS) host on a 64-bit client architecture. Select **No** (default) runs the script in a 32-bit PowerShell host.

      When setting to **Yes** or **No**, use the following table for new and existing policy behavior:

      | Run script in 64-bit PS host | Client architecture | New PS script | Existing policy PS script |
      | --- | --- | --- | --- | 
      | No | 32-bit  | 32-bit PS host supported | Runs only in 32-bit PS host, which works on 32-bit and 64-bit architectures. |
      | Yes | 64-bit | Runs script in 64-bit PS host for 64-bit architectures. When ran on 32-bit, the script runs in a 32-bit PS host. | Runs script in 32-bit PS host. If this setting changes to 64-bit, the script opens (it doesn't run) in a 64-bit PS host, and reports the results. When ran on 32-bit, the script runs in 32-bit PS host. |

    ![Add and use PowerShell scripts in Microsoft Intune](./media/mgmt-extension-add-script.png)

5. Select **OK** > **Create** to save the script.

## Assign the policy

1. In **PowerShell scripts**, select the script to assign, and then choose **Manage** > **Assignments**.

    ![Assign or deploy PowerShell script to device groups in Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Choose **Select Groups** to list available Azure AD groups. 
3. Select one or more groups that include the users whose devices receive the script. **Select** to assign the policy to the selected groups.

> [!NOTE]
> - End users aren't required to sign in to the device to execute PowerShell scripts.
> - PowerShell scripts in Intune can be targeted to Azure AD device security groups.
> - PowerShell scripts in Intune can be targeted to Azure AD user security groups.

The Intune management extension client checks once every hour with Intune. After you assign the policy to the Azure AD groups, the PowerShell script runs, and the run results are reported.

## Monitor run status

You can monitor the run status of PowerShell scripts for users and devices in the Azure portal.

In **PowerShell scripts**, select the script to monitor, choose **Monitor**, and then choose one of the following reports:

- **Device status**
- **User status**

## Troubleshoot scripts

Agent logs on the client machine are typically in `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. You can use [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) to view these log files. 

![Screenshot or sample cmtrace agent logs in Microsoft Intune](./media/apps-win32-app-10.png)  

## Delete a script

In **PowerShell scripts**, right-click the script, and select **Delete**.

## Common issues and resolutions

The PowerShell scripts don't run at every sign-in. They run only after reboots, or if the **Microsoft Intune Management Extension** service is restarted. The Intune management extension client check once per hour for any changes in the script or policy in Intune.

#### Issue: Intune management extension doesn't download

**Possible resolutions**:

- Be sure the devices are auto-enrolled in Azure AD. To confirm, on the device: 

  1. Go to **Settings** > **Accounts** > **Access work or school**.
  2. Select the joined account > **Info**.
  3. Under **Advanced Diagnostic Report**, select **Create Report**.
  4. Open the `MDMDiagReport` in a web browser, and go to the **Enrolled configuration sources** section.
  5. Look for the **MDMDeviceWithAAD** property. If this property doesn't exist, then your device isn't auto enrolled.

    [Enable Windows 10 automatic enrollment](windows-enroll.md#enable-windows-10-automatic-enrollment) includes the steps.

#### Issue: PowerShell scripts do not run

**Possible resolutions**:

- Confirm the Intune management extension is downloaded to `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Scripts don't run on Surface Hubs.
- Check the logs in `\ProgramData\Microsoft\IntuneManagementExtension\Logs` for any errors.
- For possible permission issues, be sure the properties of the PowerShell script are set to `Run this script using the logged on credentials`. Also check that the signed in user has the appropriate permissions to run the script.
- To isolate scripting problems, run a sample script. For example, create the `C:\Scripts` directory, and give everyone full control. Run the following script:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  If it succeeds, output.txt should be created, and should include the "Script worked" text.

- To test script execution without Intune, run the scripts under the System Context using the [psexec tool](https://docs.microsoft.com/sysinternals/downloads/psexec) locally:

  `psexec -i -s`

## Next steps

[Monitor](device-profile-monitor.md) and [troubleshoot](device-profile-troubleshoot.md) your profiles.
