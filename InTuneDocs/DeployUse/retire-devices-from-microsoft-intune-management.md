---
# required metadata

title: Retire devices | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Retire devices from Intune management

Whether devices are corporate-owned or personal, there comes a point when a managed device needs to be retired from management in Intune. Device retirement is relatively straight-forward; you perform either a selective wipe or a full wipe.
## Wipe data and apps from devices
Both a selective wipe and a full wipe remove the device from Intune management by removing their policy and the company portal, which means the device no longer has the credentials necessary to log on to company resources such as Microsoft SharePoint, email, or Office 365.

[Selective wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is the preferred action for employees who have enrolled their own devices in Intune because it does not affect personal information on the device. Only corporate data is removed.

For corporate-owned devices, you can also use a [full wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), which resets the device to factory settings.

## Revoke access to the company network
In the case when you are retiring a device because an employee leaves your company and they have neglected to turn in company-owned hardware, you can also [remotely lock](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) the device. This keeps both company information and company hardware from being misused, although you may have to write the device off as a loss.

You also want to revoke the license from the employee's Intune user account. This frees up the license and you can assign it to a new user  account.

## Retire hardware
Sometimes, it’s the device itself that has reached its end of life. In such cases, [resetting it to factory settings](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) with a full wipe removes all data and removes the device from Intune. Then you can get rid of the hardware according to your company’s policy.

### See also
[Help protect your data with full or selective wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)
