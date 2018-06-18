---
# required metadata

title: Custom settings for Windows 10 devices in Microsoft Intune - Azure | Microsoft Docs
description: Configure OMA-URI custom settings on devices running Windows 10 using a custom profile in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
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

# Custom OMA-URI settings for Windows 10 devices - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use the Microsoft Intune **custom** profile for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings. These settings are used to control features on devices. Windows 10 makes many Configuration Service Provider (CSP) settings available, such as [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

If you're looking for a specific setting, remember that the [Windows 10 device restriction profile](device-restrictions-windows-10.md) contains many settings that are built in to Intune, and don't require custom values.

## Configure custom settings

1. Create a new configuration profile using the **Custom** profile type. [How to configure custom device settings](custom-settings-configure.md) lists the steps.
2. In **Custom OMA-URI Settings**, select **Add** to create a new setting. You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.
3. For each OMA-URI setting you want to add, enter the following information:

- **Name**: Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
- **Description**: Optionally, enter a description for the setting.
- **OMA-URI (case sensitive)**: Enter the OMA-URI you want to supply a setting for.
- **Data type**: Choose from:
  - **String**
  - **String (XML)**
  - **Date and time**
  - **Integer**
  - **Floating point**
  - **Boolean**
  - **Base64**
- **Value**: Enter the value or file to associate with the OMA-URI you entered.

4. When you're done, select **OK**. In **Create profile**, and select **Create**. The profile is created, and is shown in the profiles list.

## Example
In the following example, the **Connectivity/AllowVPNOverCellular** setting is enabled. This setting allows a Windows 10 device to open a VPN connection when on a cellular network.

![Example of a custom policy containing VPN settings](./media/custom-policy-example.png)

## Find the policies you can configure

You’ll find a complete list of all configuration service providers (CSPs) that Windows 10 supports in the [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Not all settings are compatible with all Windows 10 versions. [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) tells you which versions are supported for each CSP.

Additionally, Intune doesn't support all the settings listed. To find out if Intune supports the setting you want, open the article for that setting. Each setting page shows it’s supported operation. To work with Intune, the setting must support the **Add** or **Replace** operations.
