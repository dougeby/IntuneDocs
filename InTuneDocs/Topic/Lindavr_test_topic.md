---
title: Lindavr test topic
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6d388b97-7a2e-4ad9-92b1-2c0c7d51217a
author: Lindavr
---
# Lindavr test topic
![](../Image/WIT_Nav_OverviewGray.png)![](../Image/WIT_Nav_GetStartedGray.png)![](../Image/WIT_Nav_EnrollDevicesGray.png)![](../Image/WIT_Nav_ConfigureDevicesGray.png)![](../Image/WIT_Nav_DeployAppsGray.png)![](../Image/WIT_Nav_ProtectResourcesGray.png)![](../Image/WIT_Nav_RetireDataDevices.png)![](../Image/WIT_Nav_TroubleshootingGray.png)![](../Image/WIT_Nav_RealworldSolutionsGray.png)![](../Image/WIT_Nav_TechnicalReferenceGray.png)

There comes a point when an employee either parts ways with the company, or with their device. In such cases, you need to be able to ensure
		   that neither the employee nor anyone using their device can access company resources. You may also want to make sure that any company 
			information on the device is removed.

## When a device is lost or stolen
When an employee loses a mobile device, or if that device is stolen, your first concern is to make sure that any company information on that device can’t be read. You also want to make sure that the device can’t be used to log on to company resources. You have several options:

-   You can [ selectively wipe company data and apps ](https://technet.microsoft.com/library/jj676679.aspx) from the device. This is the preferred action for employees who have enrolled their own devices in Intune because it does not affect personal information on the device. Selective wipe also removes the device from Intune, which means it will no longer have the credentials necessary to log on to company resources such as Microsoft SharePoint, email, or Office 365.

-   You can also [ reset a device to factory settings](https://technet.microsoft.com/library/jj676679.aspx) to make sure no data – personal or corporate – falls into the wrong hands. This is the preferred action for company-owned devices and also removes the device from Intune.

-   If company-owned iOS devices are protected by Activation Lock, you must enter the user's Apple ID and password  before you can erase or reactivate the device. This can present a challenge when users leave the company and return a company-owned device without turning off Activation Lock. To help solve this problem, you can use [Intune Activation Lock Bypass](https://technet.microsoft.com/library/mt414176.aspx).

## When an employee leaves your company
When an employee leaves your company, you also want to make that they don’t take company data with them, whether they’ve been using their own device or have neglected to turn in company-owned hardware.  In the first case, [selectively wiping the employee’s personal device](https://technet.microsoft.com/library/jj676679.aspx) is sufficient. In the second case, you can [remotely lock ](https://technet.microsoft.com/library/jj676679.aspx) it. This keeps both company information and company hardware from being misused, although you may have to write the device off as a loss.

You also want to revoke the license from the employee's Intune user account. This frees up the license and you can assign it to a new user  account.

## When you need to retire hardware
Sometimes, it’s the device itself that has reached its end of life. In such cases, [resetting it to factory settings](https://technet.microsoft.com/library/jj676679.aspx) removes all data and removes the device from Intune. Then you can get rid of the hardware according to your company’s policy.

## Inventory audits and license management
You can keep track of changes to inventory and licenses through the built-in [inventory reports](https://technet.microsoft.com/library/dn646977.aspx).

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation_for_Microsoft_Intune.md)

