---
# required metadata

title: Intune custom settings for Windows Holographic for Business devices
titlesuffix: "Azure portal"
description: Learn about the settings you can use in a Windows Holographic for Business custom profile."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
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

# Custom device settings for Windows Holographic for Business devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Use the Microsoft Intune **custom** profile for Windows Holographic for Business to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices. Windows Holographic for Business makes many configuration service providers (CSPs) settings available. For a CSP overview, see [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). For specific CSPs supported by Windows Holographic, see [CSPs supported in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

If you are looking for a particular setting, remember that the [Windows Holographic for Business device restriction profile](device-restrictions-windows-holographic.md) contains many built-in settings and do not require you to specify custom values.

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.
2. On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.
3. On the **Custom OMA-URI Settings** blade, click **Add** to add a new value. You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.
4. For each OMA-URI setting you want to add, enter the following information. Use the list in this topic to learn about the settings you can use:
	- **Setting name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.
	- **Setting description** - Optionally, enter a description for the setting.
	- **Data type** - Choose from:
		- **String**
		- **String (XML)**
		- **Date and time**
		- **Integer**
		- **Floating point**
		- **Boolean**
	- **OMA-URI (case sensitive)** - Specify the OMA-URI you want to supply a setting for.
	- **Value** - Specify the value to associate with the OMA-URI you entered.
5. When you're done, go back to the **Create Profile** blade, and click **Create**.
The profile is created and appears on the profiles list blade.

## Supported custom settings

Windows Holographic for Business supports the following custom settings:


|Setting name|OMA-URI|Data type  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Integer (0 - not allowed, 1 - allowed)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Integer (0 - not allowed, 1 - allowed)|



## How to find the policies you can configure

You can find a complete list of all configuration service providers (CSPs) that Windows Holographic supports in [CSPs supported in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Not all settings are compatible with all Windows Holographic versions. The table in the Windows topic tells you which versions are supported for each CSP.

Additionally, Intune does not support all of the settings listed in the topic. To find out if Intune supports the setting you want, open the topic for that setting. Each setting page shows it’s supported operation. To work with Intune, the setting must support the **Add** or **Replace** operations.


