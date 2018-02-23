---
# required metadata

title: Intune custom settings for Windows Holographic for Business devices
titlesuffix: "Azure portal"
description: Learn about the settings you can use in a Windows Holographic for Business custom profile."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 2/23/2018
ms.article: article
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

 Use the Microsoft Intune **custom** profile for Windows Holographic for Business to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices. Windows Holographic for Business makes many configuration service providers (CSPs) settings available. For a CSP overview, see [Introduction to configuration service providers (CSPs) for IT pros](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). For specific CSPs supported by Windows Holographic, see [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

If you are looking for a particular setting, remember that the [Windows Holographic for Business device restriction profile](device-restrictions-windows-holographic.md) contains many built-in settings and do not require you to specify custom values.

1. Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.
2. On **Create Profile**, choose **Settings** to add one or more OMA-URI settings.
3. On **Custom OMA-URI Settings**, click **Add** to add a new value. You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.
4. For each OMA-URI setting you want to add, enter the following information:
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
1. When you're done, go back to **Create Profile**, and click **Create**.
The profile is created and appears on the profiles list.

## Recommended custom settings

The following settings are useful for devices running Windows Holographic for Business:


|Setting name|OMA-URI|Data type  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Integer<br>0 - not allowed<br>1 - allowed (default)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Integer<br>0 - not allowed<br>1 - allowed (default)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Integer<br>0 – Update service is not allowed <br>1  – Update service is allowed (default).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|String<br>URL - the device checks for updates from the WSUS server at the specified URL.<br>Not configured - The device checks for updates from Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Integer<br>0 – Not configured. The device installs all applicable updates.<br>1 – The device only installs updates that are both applicable and on the Approved Updates list. Set this policy to 1 if IT wants to control the deployment of updates on devices, such as when testing is required prior to deployment.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**IMPORTANT**<br>You must read and accept the update EULAs on behalf of your end users. Failure to do so is a breach of legal or contractual obligations.|Node for update approvals and EULA acceptance on behalf of the end user.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*custom group name*/*app type*/Policy|String<br><br>For more information, see the [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) article. 

## How to find the policies you can configure

You can find a complete list of all configuration service providers (CSPs) that Windows Holographic supports in [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Not all settings are compatible with all Windows Holographic versions. The table in the Windows article tells you which versions are supported for each CSP.

Additionally, Intune doesn't support all of the settings listed in the article. To find out if Intune supports the setting you want, open the article for that setting. Each setting page shows it’s supported operation. To work with Intune, the setting must support the **Add** or **Replace** operations.
