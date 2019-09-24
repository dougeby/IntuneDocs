---
# required metadata

title: Import Wi-Fi settings for Windows devices in Microsoft Intune - Azure | Microsoft Docs
description: Export Wi-Fi settings from a Windows device as an XML file using netsh wlan. Then, import this file in Intune to create a Wi-Fi profile for devices running Windows 8.1, Windows 10, and Windows Holographic for Business.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Import Wi-Fi settings for Windows devices in Intune

For devices that run Windows, you can import a Wi-Fi configuration profile that was previously exported to a file. **For Windows 10 and later devices, you can also [create a Wi-Fi profile](wi-fi-settings-windows.md) directly in Intune**.

Applies to:  
- Windows 8.1 and later
- Windows 10 and later
- Windows 10 desktop or mobile
- Windows Holographic for Business

## Export Wi-Fi settings from a Windows device

In Windows, use `netsh wlan` to export an existing Wi-Fi profile to an XML file readable by Intune. The key must be exported in plain text to successfully use the profile.

On a Windows computer that already has the required WiFi profile installed, use the following steps:

1. Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.
2. Open up a Command Prompt as an administrator.
3. Run the `netsh wlan show profiles` command, and note the name of the profile you'd like to export. In this example, the profile name is **WiFiName**.
4. Run the `netsh wlan export profile name="ProfileName" folder=c:\Wifi` command. This command creates a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.

## Import the Wi-Fi settings into Intune

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter a **Name** and **Description** for the device restriction profile.

    > [!IMPORTANT]
    > - The name **must** be the same as the name attribute in the Wi-Fi profile xml. Otherwise, it fails.
    > - If you are exporting a Wi-Fi profile that includes a pre-shared key, you **must** add `key=clear` to the command. For example, enter:
    >   `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Using a pre-shared key with Windows 10 causes a remediation error to appear in Intune. When this happens, the Wi-Fi profile is properly assigned to the device, and the profile works as expected.
    > - If you export a Wi-Fi profile that includes a pre-shared key, be sure the file is protected. The key is in plain text, so it's your responsibility to protect the key.

4. In **Platform**, select **Windows 8.1 and later**.
5. In **Profile type**, select **Wi-Fi import**.
6. Configure the following settings:
    - **Connection name**: Enter a name for the Wi-Fi connection. This name is displayed to end users when they browse available Wi-Fi networks.
    - **Profile XML**: Select the browse button, and choose the XML file that contains the Wi-Fi profile settings you want to import.
    - **File contents**: Shows the XML code for the configuration profile you selected.
7. When you're done, select **OK** > **Create** to save your changes. The profile is created and is shown in the profiles list.

## Next steps

The profile is created, but it's not doing anything. Next, [assign this profile](../device-profile-assign.md).

## More resources

[Wi-Fi settings overview](../wi-fi-settings-configure.md), including other available platforms.
