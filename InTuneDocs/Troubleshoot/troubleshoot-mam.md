---
# required metadata

title: [Troubleshoot mobile application management | Microsoft Intune]
description:
keywords:
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: joglocke
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot mobile application management

If you are having problems with mobile application management, start here. This topic contains some common problems you might encounter together with solutions.


**Issue:** MAM without Enrollment policy from Azure console is not applying to the Skype for Business app on iOS and Android devices.

Resolution: Skype for Business must be set up for modern authentication.  Please follow instructions in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) to set up modern authentication for Skype.

**Issue:** MAM without Enrollment policies are not applying to any (supported Office App)[https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] for any user.
 
Resolution: Confirm that the user is licensed for Intune.  

**Issue:** IT admin user is unable to configure MAM policies in Azure Portal

Resolution:
The following roles have access to the Azure Portal:

- Global administrator, which you can set up in the [Office Portal](http://portal.office.com/)
- Owner, which you can set up in the [Azure Portal](https://portal.azure.com/).
- Contributor, which you can set up in the [Azure Portal](https://portal.azure.com/).

Refer to [Get ready to configure mobile app management policies with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) for help  setting up these roles. 

**Issue:** App report does not show user(s) we recently targeted MAM policy to.

Resolution: If a user is newly targeted with a MAM policy, it can take up to 24 hours for that user to show up in reports as a targeted user. 

**Issue:** Policy changes/updates can take up to 8 hours to apply.  

Resolution: End user can log out of the app and log back in to force sync with service .  

**Issue:** MAM policy is not applying to Apple DEP devices

Resolution: Please ensure you are using User Affinity with Apple Device Enrollment Program (DEP). User Affinity is required for any app that requires user authentication under DEP.
Refer to [Enroll corporate-owned Device Enrollment Program iOS devices](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) for more information on iOS DEP enrollment.


### See also
- [Validating your mobile application management setup](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Get ready to configure mobile app management policies with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 


