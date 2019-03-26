---
# required metadata

title: Use StageNow logs on Android Zebra devices in Microsoft Intune - Azure | Microsoft Docs
description: See common issues and resolutions when using StageNow on Android devices with Microsoft Intune. Also learn how to get logs, and see examples of how to read the logs for success or errors.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority:
ms.technology:
ms.assetid: 

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

# Use StageNow logs to troubleshoot, and see potential issues on Android Zebra devices in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can use [**Zebra Mobility Extensions (MX)** to manage Android Zebra devices](android-zebra-mx-overview.md). When using Zebra devices, you create profiles in StageNow to manage settings, and upload them to Intune. Intune uses the StageNow app to apply the settings on the devices. The StageNow app also creates a detailed log file on the device that's used to troubleshoot.

This feature applies to:

- Android

For example, you create a profile in StageNow to configure a device. When you create the StageNow profile, the last step generates a file for you test the profile. You consume this file with the StageNow app on the device.

In another example, you create a profile in StageNow, and test it. In Intune, you add the StageNow profile, and then assign it to your Zebra devices. When checking the status of the assigned profile, the profile shows a high-level status. You want more details.

In both these cases, you can get more details from the StageNow log file, which is saved on the device every time a StageNow profile applies.

This article shows you how to read the StageNow logs, and lists some potential issues with Zebra devices.

[Use and manage Zebra devices with Zebra Mobility Extensions](android-zebra-mx-overview.md) has more information on this feature.

## Read the logs

When looking at the logs, there's an error whenever you see the `<characteristic-error>` tag. Error details are written to the `<parm-error>` tag > `desc` property.

## Error types

Zebra devices include different error reporting levels:

- The CSP isn't supported on device. For example, the device isn't a cellular device and doesn't have a cellular manager.
- The MX or OSX version is mismatched. Each CSP is versioned. For a full support matrix, see [Zebra's documentation](http://techdocs.zebra.com/mx/) (opens Zebra's web site).
- The device reports another issue or error.

## Examples

For example, you have the following input profile:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

In the log, the XML is identical to the input. This matching output means the profile successfully applied to the device with no errors:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

In another example, you have the following input:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

The log shows an error, as it contains a `<characteristic-error>` tag. In this scenario, the profile tried to install an Android package (APK) that doesn't exist in the given path:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## Potential issues with Zebra devices

This section lists possible issues you may run into when using Zebra devices with Device Administrator.

### Android System WebView is out of date

When older devices sign in using the Company Portal app, users may see a message that the System WebView component is out of date, and needs upgraded. If the device has Google Play installed, connect it to the internet, and check for updates. If the device doesn't have Google Play installed, get the updated version of the component, and apply it to the devices. Or, update to the latest device OS issued by Zebra.

### Management actions take a long time

If Google Play services aren't available, some tasks take up to 8 hours to finish. [Limitations of Intune Company Portal app for Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (opens another Microsoft web site) may be a good resource.

### “Device spoofing suspected” shows in Intune

This error means that Intune suspects a non-Zebra Android device is reporting its model and manufacturer as a Zebra device.

### Company Portal app is older than minimum required version

Intune may update the minimum required version of the Company Portal app. If Google Play isn't installed on the device, the Company Portal app doesn't get automatically updated. If the minimum required version is newer than the installed version, the Company Portal app stops working. Update to the latest Company Portal app using [sideloading on Zebra devices](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## Next steps

[Zebra discussion boards](https://developer.zebra.com/community/home/discussions) (opens Zebra's web site)

[Use and manage Zebra devices with Zebra Mobility Extensions in Intune](android-zebra-mx-overview.md)
