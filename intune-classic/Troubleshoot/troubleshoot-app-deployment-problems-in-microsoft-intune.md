---
# required metadata

title: Troubleshoot app deployment problems 
description: This topic helps you solve app deployment problems with Microsoft Intune.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot app deployment problems in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

If you are having problems deploying and managing apps with Intune, start here. This topic contains some common problems you might encounter together with solutions.

## Common app deployment error codes

|Error code|Possible problem|Suggested resolution|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (client error)|To install this app, you must have a sideloading-enabled system.|Make sure that the app package is signed with a trusted signature and installed on a domain-joined device that has the AllowAllTrustedApps policy enabled, or a device that has a Windows Sideloading license with the AllowAllTrustedApps policy enabled.|
|0x80073CF0|The package could not be opened.|Possible causes:<br /><br />-   The package is unsigned.<br />-   The publisher name does not match the signing certificate subject.<br /><br />Check the AppxPackagingOM event log for more information.|
|0x80073CF3|The package failed update, dependency, or conflict validation|Possible causes:<br /><br />-   The incoming package conflicts with an installed package.<br />-   A specified package dependency is not found.<br />-   The package does not support the correct processor architecture.<br /><br />Check the AppXDeployment-Server event log for more information.|
|0x80073CFB|The provided package is already installed, and reinstallation of the package is blocked|You might receive this error if you are installing a package that is not identical to the package that is already installed. Confirm the digital signature is also part of the package. When a package is rebuilt or re-signed, that package is no longer bitwise identical to the previously installed package. Two possible options to fix this error are as follows:<br /><br />-   Increment the version number of the app, then rebuild and re-sign the package.<br />-   Remove the old package for every user on the system before you install the new package.|
|0x87D1041C|Application installation succeeded but application is not detected.|- The app was deployed successfully by Intune, then subsequently uninstalled (possibly by the end user). Instruct the user to reinstall the app from the company portal. Required apps will be reinstalled automatically when the device next checks in.|

## Troubleshooting apps from the Microsoft Store

The information in the topic [Troubleshooting packaging, deployment, and query of Microsoft Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) helps you troubleshoot common problems you might encounter when installing apps from the Microsoft Store, whether by using Intune, or by any other means.

## Troubleshooting app deployment to PCs managed by the Intune software client
To help you troubleshoot problems deploying apps to the PCs managed by the Intune software client, you can look a the following two log files:
- %ProgramFiles%\Microsoft\OnlineManagement\Logs folder
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Additionally, if you need to open a support case for Intune, it will be helpful to also send these logs to Microsoft.


### Next steps
If this troubleshooting information  didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
