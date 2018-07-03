---
# required metadata

title: Import Wi-Fi settings for Windows 8.1 and later
titleSuffix: Microsoft Intune
description: How to import Wi-Fi settings from Windows into an Intune Wi-Fi profile.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Import Wi-Fi settings for Windows 8.1 and later devices in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

For devices that run Windows 8.1, Windows 10 desktop or mobile, or Windows Holographic for Business, you can import a Wi-Fi configuration profile that was previously exported to a file.

## Export Wi-Fi settings from a Windows device

In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune. The key must be exported in plain text to successfully use the profile.

On a Windows computer that already has the required WiFi profile installed, use the following steps:

1. Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.
2. Open up a Command Prompt as an administrator.
3. Run the `netsh wlan show profiles` command, and note the name of the profile you'd like to export. In this example, the profile name is **WiFiName**.
4. Run the `netsh wlan export profile name="ProfileName" folder=c:\Wifi` command.This creates a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.

## Import the Wi-Fi settings into Intune

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device configuration** > **Profiles** > **Create profile**.
4. Enter a **Name** and **Description** for the device restriction profile.

    > [!IMPORTANT]
    > - The name **must** be the same as the name attribute in the Wi-Fi profile xml. Otherwise, it fails.
    > - If you are exporting a Wi-Fi profile that includes a pre-shared key, you **must** add `key=clear` to the command. For example, enter:
    >    `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Using a pre-shared key with Windows 10 causes a remediation error to appear in Intune. When this happens, the Wi-Fi profile is properly assigned to the device, and the profile works as expected.
    > - If you export a Wi-Fi profile that includes a pre-shared key, be sure the file is protected. The key is in plain text, so it's your responsibility to protect the key.

5. In **Platform**, select **Windows 8.1 and later**.
6. In **Profile type**, select **Wi-Fi import**.
7. Configure the following settings:
  - **Connection name**: Enter a name for the Wi-Fi connection. This name is displayed to end users when they browse available Wi-Fi networks.
  - **Profile XML**: Select the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.
  - **File contents**: Shows the XML code for the configuration profile you selected.
8. When you're done, choose **OK**, and then **Create** the profile.

The profile is created, and is in the profiles list.
