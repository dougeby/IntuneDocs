---
# required metadata

title: App based conditional access to 0365 | Microsoft Intune
description: Understand the concepts of how MAM CA can help with controlling what apps have access to O365 services.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Allow only mobile apps that support Intune MAM policies to access O365 services
Intune mobile app management (MAM) policies help protect your company data on devices that are enrolled for management in Intune, but also on BYOD devices that are not enrolled for management in Intune.  In both these cases, but especially in the case where the devices are not managed, you may want to make sure that only mobile apps that support MAM policies are used to access your company resources. By implementing conditional access for apps with MAM policies (which we will call MAM CA), you can create a policy that allows only mobile apps that support Intune MAM policies to access O365 services like Exchange Online and SharePoint Online.


The diagram below illustrates what we just described above.  With MAM, you can configure policies that prevent corporate data from being transferred to the device or to non-protected apps. With MAM CA, access to cloud apps like Exchange Online and SharePoint online can be managed.

![Diagrammatic representation of data protection by MAM policies and MAM CA](../media/mam-ca-with_mam-policy.png)

## Some examples on how MAM CA can be used
* Block mobile apps that don’t have Intune MAM support from accessing SharePoint Online.
* Block the built-in mail apps on iOS and Android from sync'ing email from Exchange Online.


## Supported apps
**Exchange Online**
* Microsoft Outlook for Android and iOS

**SharePoint Online**
* Microsoft Word for iOS and Android
* Microsoft Excel for iOS and Android
* Microsoft PowerPoint for iOS and Android
* Microsoft OneDrive for Business for iOS and Android
* Microsoft OneNote for iOS


>[!IMPORTANT]
>Microsoft Excel, PowerPoint, Word, Skype for Business, and OneNote apps for iOS and Android are bundled together as a single option. The OneNote app for Android does not yet support MAM without enrollment.

## Overlap with other conditional access and authentication methods
### MAM CA with Azure Active Directory Certificate Based Authentication

MAM CA must not be used with Azure Active Directory (Azure AD) Certificate Based Authentication (CBA). You can only have one of these configured at a time.
### MAM CA with conditional access based on device compliance  

[Conditional access based on device compliance](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Device CA**) can be configured through the [Intune administrator console](https://manage.microsoft.com) or the [Azure AD Premium management console] (https://manage.windowsazure.com). Device CA require users to connect to SharePoint Online and Exchange Online only through Intune managed  devices that are compliant with the Intune device compliance policy or domain joined PCs.  If a user belongs to one or more security groups that are targeted for both  MAM CA and Device CA policies, the user must meet one of the two requirements:
* The app used to access the service is a mobile app that is supported by MAM CA, and the device that the app is running on, has iOS Authenticator (for iOS devices), or the Company Portal app (for Android devices) installed.
* The device used to access the service is Intune managed and compliant with the Intune device compliance policy, or it is a domain joined PC.  Here are some examples to help illustrate this:
* If a user is targeted by both a MAM CA policy and a Device CA policy and tries to connect from the OneDrive app, they will be able to access company files on SharePoint online if one of the two following conditions is true:
  * OneDrive is supported by MAM CA.
  * The device that is used to access is compliant with the Intune device compliance policy.  
* If a user tries to connect from the native iOS email app, he or she will be required to be on a managed and compliant device since the native mail app supported by MAM CA.
* If a user tries to connect from a Windows home PC, the Device CA policy will apply, requiring that the he or she must use a domain joined PC.


## What to expect when using an app with MAM CA
MAM CA verifies the identity of the approved application via a broker app that must be present on the device:
*  On iOS, the Azure Authenticator app is the broker app.
* On Android, the Intune Company Portal app is the broker app. 

End-users signing in to an app that is supported by MAM CA like OneDrive or Outlook for the first time are prompted install the broker app and register the device with Azure AD. Device registration in Azure AD (previously known as Workplace Join) will create a device record and certificate against which tokens are issued.  It is important to note that this is **not** the same as MDM enrollment. There are no management profiles or policies that are applied, and there is no inventory taken of apps on the device.  The process of installing the broker app and registering the device will only happen on the first use of a managed app.


## Next steps
[Create an Exchange Online Policy for MAM apps](mam-ca-for-exchange-online.md)

[Create a SharePoint Online Policy for MAM apps](mam-ca-for-sharepoint-online.md)
### See also
[Block apps that do not have modern authentication](block-apps-with-no-modern-authentication.md)

[Protect app data with MAM policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
