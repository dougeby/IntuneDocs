---
# required metadata

title: Enable BYOD with Microsoft Intune
description: A high-level workflow for setting up Intune to enable a bring-your-own-device (BYOD) solution to your organization.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: vlpetros
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Enable BYOD with Intune

This topic provides a high-level workflow for setting up Intune to enable a bring-your-own-device (BYOD) solution to your organization. It organizes the task into three processes and links to supporting how-to topics.

The workflow is divided into the following three processes. You can tailor aspects of each process to meet your organization’s requirements.

-   **[Enroll devices and check for compliance](#enroll-devices-and-check-for-compliance)** describes how to enable users to enroll their personal devices into management with Intune. Intune manages iOS, macOS, Android, and Windows devices. This section also describes how to deploy policies to devices and ensure they meet basic security requirements.

- **[Provide access to company resources](#provide-access-to-company-resources)** shows you how you can enable users to access company resources easily and securely. You do this by deploying access profiles to managed devices. This section also explains how to manage volume-purchased app deployments with Intune.

-   **[Protect company data](#protect-company-data)** helps you learn how to provide conditional access to company resources, prevent data loss, and remove company apps and data from devices when they are no longer needed for work or have been lost or stolen.

[![High-level workflow diagram for enabling BYOD with Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## Before you begin
Before users can enroll devices, you first need to prepare the Intune service itself. To do so, [assign licenses to users](licenses-assign.md) and [set the mobile device management authority](mdm-authority-set.md).

While you're at it, you should also [customize the company portal](company-portal-customize.md). Add company branding and provide users with support information. This creates a trusted enrollment and support experience for your users. You can also create [terms of use](terms-and-conditions-create.md) that users must accept before enrolling, or [device restrictions](enrollment-restrictions-set.md) to specify which platforms you support.

## Enroll devices and check for compliance

After you prepare the Intune service, you need to meet the various enrollment requirements for the different device types that you want to manage. The process to enroll devices into management is straightforward, but differs slightly based on device type.

-   **iOS and Mac devices** You need to [get an Apple MDM push certificate](apple-mdm-push-certificate-get.md) to enroll iPads, iPhones, or macOS devices. After you've uploaded your MDM push certificate to Intune, users can [enroll iOS devices](/intune-user-help/enroll-your-device-in-intune-ios) using the Company Portal app and use the Company Portal website to [enroll macOS devices](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Android devices** There's nothing you need to do to get the Intune service ready to enroll Android devices. Users can just [enroll their Android devices](/intune-user-help/enroll-your-device-in-intune-android) into management using the Company Portal app available from Google Play.

-   **Windows Phones and PCs** Windows devices can be enrolled with additional configuration. You can enable automatic enrollment for Windows 10 PCs and Windows 10 mobile devices in Azure Active Directory (AD) Premium to simplify the end user experience. If you don't have Azure AD Premium or if you need to support Windows 8.1, you can create [a DNS alias for the enrollment server](windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium) to make enrollment easier.


### Make sure that managed devices meet basic security requirements

After users enroll their devices into management, IT needs to make sure that devices used to access company apps and data meet basic security requirements. These rules might include using a PIN to access devices and encrypting data stored on devices. A set of such rules is called a [compliance policy](device-compliance.md).

When you [deploy a compliance policy](device-compliance-get-started.md) to a user, Intune checks each device the user has managed by Intune to see if the device meets the basic security requirements you defined as part of your BYOD policy. After a device has been evaluated for policy compliance, it reports its status back to Intune. In some cases, users might be asked to fix settings, such as their PIN or device encryption. Other times, the company portal app simply notifies the user about any settings that don't meet your policy.

## Provide access to company resources

The first thing most employees want to access on their mobile device is company email and documents. They expect to set it up without going through complex steps or calling the help desk. Intune makes it easy for you to [create and deploy email settings](email-settings-configure.md) for native email apps that are pre-installed on mobile devices.


> [!NOTE]
> Intune supports Android for Work email profile configuration for the Gmail and Nine Work email apps found in the Google Play store.

Intune also helps you control and protect access to on-premises company data when users work offsite. Intune [Wi-Fi](wi-fi-settings-configure.md), [VPN](vpn-settings-configure.md), and email profiles work together to permit access to the files and resources that they need to do their work wherever they are. Your company's web applications and services hosted on-premises can also be securely accessed and protected using the Azure Active Directory Application Proxy and conditional access.

### Manage volume-purchased apps
With Intune, it is easy to:
* Import the volume license information from either app store
* Track how many licenses you have used
* Prevent your users from installing more copies of the app than you own
* [Deliver store apps to managed devices](apps-deploy.md)
* Target apps to unmanaged devices using the company portal website

Intune also allows you to manage and deploy apps that you purchased in volume from the iOS app store and the Microsoft Store for Business. This helps you reduce the administrative overhead of tracking volume-purchased apps.

> [!TIP]
> You can [configure Single Sign On (SSO) with Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). SSO lets users sign into apps with the domain user name and password they use on-premises. Also, you can [provide internet-based access to web apps hosted on-premises](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) using the Azure Active Directory Application Proxy.

-   [Manage volume-purchased apps for iOS devices](vpp-apps-ios.md). You buy multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). You need to set up an Apple VPP account from the Apple website and upload the Apple VPP token to Intune. You can then synchronize your volume-purchase information with Intune and track your volume-purchased app use.

-   [Manage apps purchased from the Microsoft Store for Business](windows-store-for-business.md). The [Microsoft Store for Business](https://www.microsoft.com/business-store) gives you a place to find and buy apps for your organization, individually, or in volume. By connecting the store to Intune, you can manage volume-purchased apps from the Azure portal.

## Protect company data

Intune protects company data through many technology layers. At the identity layer, conditional access protects access to services. Conditional access only allows managed and compliant devices to access company resources. At the client app layer, app protection policies protects against data loss. App protection policies prevent data from moving to apps or storage locations that are not protected. These policies also let you wipe company data when a device is lost or stolen.

### Enforce conditional access to company resources

You can combine compliance policies with [conditional access policies](device-compliance.md) to check if devices meet the basic security requirements that your BYOD policy requires. If a device doesn't meet the requirements, rules are enforced and access is denied until the device meets policy requirements. This ensures that only managed and compliant devices can access company data from services like Exchange ([Exchange On-premises](exchange-connector-install.md) or [Exchange Online](conditional-access-exchange-create.md), SharePoint Online, Skype for Business Online, and others.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Conditional access policies will not work if there is no compliance policy in place to validate compliance.

### Prevent data loss of company data with app protection policies

With Intune app protection policies, you can choose how your data is accessed, with or without device enrollment. This versatility lets you protect company data so that even if a user doesn't enroll their device into Intune, they can still access company data securely.

You can use [Intune app protection policies](app-protection-policies.md) to help protect company data that is accessed by iOS and Android devices. When you use these app-level policies, you can control how company data is used and shared by employees even if the device itself isn’t managed by Intune

Use [Windows Information Protection (WIP)](app-protection-policies-configure-windows-10.md) to do the same for managed Windows 10 devices. These policies work without interfering with the employee experience. They do not require changes to your network environment or other apps.

### Remove company data while leaving personal data intact

When a device is no longer needed for work, is being repurposed, or has gone missing, you can remove company apps and data from it. To do this, you can use Intune's remove company data and factory reset capabilities. Your users can also remotely reset their own personally owned devices from the Intune Company Portal if those devices are enrolled in Intune.

A [factory reset](devices-wipe.md) restores a device to its factory default settings, removes user data and settings, and removes the device from Intune management. [Remove company data](devices-wipe.md#remove-company-data) removes only company data from the device but leaves users’ personal data intact.

Once initiated, the device immediately begins the reset process. When the process is complete, all company data is deleted and the device name is removed from the Intune. This ends the device management lifecycle.
