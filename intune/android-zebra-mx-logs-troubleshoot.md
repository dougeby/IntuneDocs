---
# required metadata

title: Use StageNow logs on Android Zebra devices in Microsoft Intune - Azure | Microsoft Docs
description: See common issues and resolutions whne using StageNow on Android devices with Microsoft Intune. Also read the logs, and see examples of how to read the logs for success or errors.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/12/2019
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

# Use StageNow logs to troubleshoot Android Zebra devices in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can use [**Mobility Extensions (MX)** to manage Android Zebra devices](android-zebra-mx-overview.md). When using Zebra devices, you create profiles in StageNow to test your settings. After your create the StageNow profile, test it by generating a barcode or sound file. Then, use this file in the StageNow app on the device. The StageNow app creates a detailed log file on the device that's used to troubleshoot.

This feature applies to:

- Android

For example, you create a profile in StageNow to disable WiFi. In Intune, you add the StageNow profile, and then assign it to your Zebra devices. When checking the status of the profile assignment in Intune, the profile shows a failure. You can get more details from the StageNow log file, which is saved on the device every time a StageNow profile applies.

This article shows you how to read the StageNow logs, and lists some potential issues. For more information on how to use MX on Zebra devices in Intune, see [Use and manage Zebra devices with Mobility Extensions in Intune](android-zebra-mx-overview.md).

## Read the logs

When looking at the logs, there's an error whenever you see `<characteristic-error>` tag. Error details are written to the `<parm-error>` > `desc` property.

Zebra devices include different error reporting levels:

- The CSP isn't supported on device. For example, the device isn't a cellular device and doesn't have a cellular manager.
- The MX version is mismatched. Each CSP is versioned. For a full support matrix, see [Zebra's documentation](http://techdocs.zebra.com/mx/) (opens Zebra's web site).
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

In the log, the XML is identical to the input. This output means the profile successfully applied to the device with no errors:

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

The log shows an error. In this scenario, the profile tried to install an Android package (APK) that doesn't exist in the given path:

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

## Potential issues

This section lists possible issues you may run into when using Zebra devices with Device Administrator.

### Android System WebView is out of date

When older devices sign in using the Company Portal app, the logs show a message that the System WebView component is out of date, and needs upgraded to continue. If the device doesn't have Google Play installed, get the updated version of the component, and apply it to the devices. Or, update to the latest device OS issued by Zebra.

### Management actions taking a long time

If Google Play services aren't available, some tasks take up to 8 hours to finish. [Limitations of Intune Company Portal app for Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) may be a good resource.

### “Device spoofing suspected” shows in Intune

This error means that Intune suspects a non-Zebra Android device is reporting its model and manufacturer as a Zebra device.

## Next steps

[Zebra discussion boards](https://developer.zebra.com/community/home/discussions) (opens Zebra's web site)
