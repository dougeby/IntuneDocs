---
title: Troubleshoot app deployment problems in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
author: Nbigman
---
# Troubleshoot app deployment problems in Microsoft Intune
This topic provides resources to help you solve app deployment problems with[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

## <a name="BKMK_TypicalProblems"></a>Help for typical app deployment problems

#### If you can’t log in to the [!INCLUDE[wit_iwportal_1](../Token/wit_iwportal_1_md.md)]

1.  Check to see if your account exists in the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)] or if it is disabled.

2.  Make sure that you are provisioned on this account in the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)].

3.  In the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)], make sure that you are using the right user name and password to log in to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and that it is in the format: **joe@domain.com**.

#### If the Contact IT information is missing in the company portal

1.  In the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], click **Admin** &gt; **Company Portal**.

2.  Set the **Contact IT** details.

#### If you can’t see specific apps in the list

1.  Make sure you are checking the list of apps for a user or device to which the app was deployed.

2.  Make sure that the device meets the necessary device requirements.

#### If you receive an error while downloading an app

1.  Make sure there are not too many concurrent downloads per user. Each user can download one app at a time.

2.  Make sure there are not too many concurrent downloads per account. Wait a few minutes and then try again.

3.  If you receive an iOS native message that you can't install, that the installation is canceled or that you need to retry, it might be due to momentary high traffic. Wait a few minutes and then try again.

4.  If the iOS app download progress bar is complete but the app installation fails, something might be wrong with the app files that you provided.

#### If clicking a link to an iOS app takes you to a previous location in the iTunes App Store

1.  The current iTunes App Store session is opening to the previous app page.

2.  Close the iTunes App Store on the device and retry the link.

#### If you receive an error while launching an iOS app

1.  The expiration date of the app might not be valid.

#### If your app is stuck “in progress” while uploading

1.  When uploading an app, first the metadata is added, followed by the app package. After the metadata has been uploaded, the app will appear in progress. If you see that your app is in the in progress state for an unusually long time, delete the app and then upload it again.

2.  Make sure not to manage the deployment of the app while it is in the “in progress” state.

#### If you encounter a failure when installing an iOS app

1.  Make sure that your organization’s firewall allows access to the Apple provisioning and certification web sites.

2.  For more information, view the Apple developer documentation.

#### If managed apps are not reporting installation status

-   Installation status was not collected for managed app installations prior to the Microsoft Intune service update in November 2014. For devices that installed managed apps prior to this service update, update each associated app deployment with the appropriate deployment action (for example, **Available install**). Each device will update the app during the automatic check for available apps. For more information, see [Update apps using Microsoft Intune](../Topic/Update_apps_using_Microsoft_Intune.md).

## <a name="BKMK_SoftDistErrorCodes"></a>App deployment error codes
The following table lists common errors that may occur during [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] app deployment, the likely causes, and possible solutions to help you troubleshoot them.

|Error code|Possible problem|Suggested resolution|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (client error)|To install this app, you must have a sideloading-enabled system.|Make sure that the app package is signed with a trusted signature and installed on a domain-joined device that has the AllowAllTrustedApps policy enabled, or a device that has a Windows Sideloading license with the AllowAllTrustedApps policy enabled (applied when a Windows RT device is enrolled).|
|0x80073CF0|The package could not be opened.|Possible causes:<br /><br />-   The package is unsigned.<br />-   The publisher name does not match the signing certificate subject.<br /><br />Check the AppxPackagingOM event log for more information.|
|0x80073CF3|The package failed update, dependency, or conflict validation|Possible causes:<br /><br />-   The incoming package conflicts with an installed package.<br />-   A specified package dependency is not found.<br />-   The package does not support the correct processor architecture.<br /><br />Check the AppXDeployment-Server event log for more information.|
|0x80073CFB|The provided package is already installed, and reinstallation of the package is blocked|You might receive this error if you are installing a package that is not identical to the package that is already installed. Confirm the digital signature is also part of the package. When a package is rebuilt or re-signed, that package is no longer bitwise identical to the previously installed package. Two possible options to fix this error are as follows:<br /><br />-   Increment the version number of the app, then rebuild and re-sign the package.<br />-   Remove the old package for every user on the system before you install the new package.|

## See Also
[Troubleshoot Microsoft Intune](../Topic/Troubleshoot_Microsoft_Intune.md)
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy_and_configure_apps_with_Microsoft_Intune.md)

