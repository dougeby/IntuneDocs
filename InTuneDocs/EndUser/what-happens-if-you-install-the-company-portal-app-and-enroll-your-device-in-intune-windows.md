---
# required metadata

title: What happens if you install the Company Portal app and enroll your Windows device in Intune? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# What happens if you install the Company Portal app and enroll your Windows device in Intune?

When you install the Company Portal app and then use it to enroll a Windows or Windows Phone device, you are letting your IT admin manage your device to help keep company or school data secure. This topic describes what happens for devices earlier than Windows 10. For Windows 10 devices, see the [related topic](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## What happens to all Windows devices after enrollment
Enrolling your Windows or Windows Phone device in Intune lets you:

-   Access the company’s network, and your email and work files.

-   Get company apps from the Company Portal website. (For Windows 7 and Windows Vista, you can get company apps from the Company Portal website only.)

-   Automatically set up your company or school email account.

-   Reset your phone to factory settings if it is lost or stolen.

When you enroll your device, you are giving your IT admin permission to do things like:

-   Reset your device back to the manufacturer’s default settings. This is helpful if the device is lost or stolen.

-   Remove only company-related files and business apps. *Your personal data and settings aren’t removed.*

-   Your IT admin can see the software installed on the device, including software you have personally installed.

-   Set requirements on your device, like requiring you to have a device password or PIN to help protect company data. Your IT admin might also limit how many times you can enter an incorrect password, and might lock you out of the device if you try too many times.

-   Require you to encrypt the data on your device to help protect company data, in case your device is lost or stolen.

-   Require you to accept terms and conditions.

-   Prevent you from taking pictures of company-related data.

## What happens to all Windows PCs after enrollment

-  Software will be installed on your computer to let your IT admin manage the computer, and to let you access company resources like apps and support information. Your IT admin might automatically update this software.

-  Intune Endpoint Protection might be installed on your computer. This software checks for viruses and malware.

-  Your IT admin can collect or delete data from your computer’s hard drive.

-  Your IT admin can install apps and updates on your computer.

## What happens every eight hours after device enrollment
About every eight hours, enrolled devices will:

-   Download any policy or app updates that your IT admin has made available.

-   Send any hardware inventory updates.

-   Send any company app inventory updates.

If you have questions, contact your IT admin. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
