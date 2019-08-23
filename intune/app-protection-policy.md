---
# required metadata

title: App protection policies overview
titleSuffix: Microsoft Intune
description: Learn how Microsoft Intune app protection policies help protect your company data and prevent data loss.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
---

# App protection policies overview

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

App protection policies (APP) are rules that ensure an organization's data remains safe or contained in a managed app. A policy can be a rule that is enforced when the user attempts to access or move "corporate" data, or a set of actions that are prohibited or monitored when the user is inside the app. A managed app is an app that has app protection policies applied to it, and can be managed by Intune.

Mobile Application Management (MAM) app protection policies allows you to manage and protects your organization's data within an application. With **MAM without enrollment** (MAM-WE), a work or school-related app that contains sensitive data can be managed on almost any [device](app-management.md#app-management-capabilities-by-platform), including personal devices in **bring-your-own-device** (BYOD) scenarios. Many productivity apps, such as the Microsoft Office apps, can be managed by Intune MAM. See the official list of [Microsoft Intune protected apps](apps-supported-intune-apps.md) available for public use.

## How you can protect app data
Your employees use mobile devices for both personal and work tasks. While making sure your employees can be productive, you want to prevent data loss, intentional and unintentional. You'll also want to protect company data that is accessed from devices that are not managed by you.

You can use Intune app protection policies **independent of any mobile-device management (MDM) solution**. This independence helps you protect your company’s data with or without enrolling devices in a device management solution. By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.

### App protection policies on devices

App protection policies can be configured for apps that run on devices that are:

- **Enrolled in Microsoft Intune:** These devices are typically corporate owned.

- **Enrolled in a third-party Mobile device management (MDM) solution:** These  devices are typically corporate owned.

  > [!NOTE]
  > Mobile app management policies should not be used with third-party mobile app management or secure container solutions.

- **Not enrolled in any mobile device management solution:** The devices are typically employee owned devices that aren't managed or enrolled in Intune or other MDM solutions.

> [!IMPORTANT]
> You can create mobile app management policies for Office mobile apps that connect to Office 365 services. You can also protect access to Exchange on-premises mailboxes by creating Intune app protection policies for Outlook for iOS and Android enabled with hybrid Modern Authentication. Before using this feature, make sure you meet the [Outlook for iOS and Android requirements](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). App protection policies are not supported for other apps that connect to on-premises Exchange or SharePoint services.

## Benefits of using App protection policies

The important benefits of using App protection policies are the following:

- **Protecting your company data at the app level.** Because mobile app management doesn't require device management, you can protect company data on both managed and unmanaged devices. The management is centered on the user identity, which removes the requirement for device management.

- **End-user productivity isn't affected and policies don't apply when using the app in a personal context.** The policies are applied only in a work context, which gives you the ability to protect company data without touching personal data.

- **App protection policies makes sure that the app-layer protections are in place.** For example, you can:
  - Require a PIN to open an app in a work context 
  - Control the sharing of data between apps 
  - Prevent the saving of company app data to a personal storage location

- **MDM, in addition to MAM, makes sure that the device is protected**. For example, you can require a PIN to access the device, or you can deploy managed apps to the device. You can also deploy apps to devices through your MDM solution, to give you more control over app management.

There are additional benefits to using MDM with App protection policies, and companies can use App protection policies with and without MDM at the same time. For example, consider an employee that uses both a phone issued by the company, and their own personal tablet. The company phone is enrolled in MDM and protected by App protection policies while the personal device is protected by App protection policies only.

If you apply a MAM policy to the user without setting the device state, the user will get the MAM policy on both the BYOD device and the Intune-managed device. You can also apply a MAM policy based on the managed state. So when you create an app protection policy, next to **Target to all app types**, you'd select **No**. Then do any of the following:
- Apply a less strict MAM policy to Intune managed devices, and apply a more restrictive MAM policy to non MDM-enrolled devices.
- Apply a MAM policy to unenrolled devices only.

## Supported platforms for app protection policies

Intune offers a range of capabilities to help you get the apps you need on the devices you want to run them on. For more information, see [App management capabilities by platform](app-management.md#app-management-capabilities-by-platform).

Intune app protection policies platform support aligns with Office mobile application platform support for Android and iOS devices. For details, see the **Mobile apps** section of [Office System Requirements](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

> [!IMPORTANT]
> The Intune Company Portal is required on the device to recieve App Protection Policies on Android. For more information, see the [Intune Company Portal access apps requirements](end-user-mam-apps-android.md#access-apps).

## How app protection policies protect app data

### Apps without app protection policies

When apps are used without restrictions, company and personal data can get intermingled. Company data can end up in locations like personal storage or transferred to apps beyond your purview and result in data loss. The arrows in the following diagram show unrestricted data movement between both corporate and personal apps, and to storage locations.

![Conceptual image for data movement between apps with no policies in place](./media/apps-without-protection-policies.png)

### Data protection with app protection policies (APP)

You can use App protection policies to prevent company data from saving to the local storage of the device (see the image below). You can also restrict data movement to other apps that aren't protected by App protection policies. App protection policy settings include:
- Data relocation policies like  **Prevent Save As**, and **Restrict cut, copy, and paste**.
- Access policy settings like **Require simple PIN for access**, and **Block managed apps from running on jailbroken or rooted devices**.

![Conceptual image that shows company data being protected by policies](./media/apps-with-protection-policies.png)

### Data protection with APP on devices managed by an MDM solution

The below illustration shows the layers of protection that MDM and App protection policies offer together.

![Image that shows how App protection policies work on BYOD devices](./media/app-protection-policies-with-mdm.png)

The MDM solution adds value by providing the following:

- Enrolls the device
- Deploys the apps to the device
- Provides ongoing device compliance and management

The App protection policies add value by providing the following:

- Help protect company data from leaking to consumer apps and services
- Apply restrictions like *save-as*, *clipboard*, or *PIN*, to client apps
- Wipe company data when needed from apps without removing those apps from the device

### Data protection with APP for devices without enrollment

The following diagram illustrates how the data protection policies work at the app level without MDM.

![Image that shows how App protection policies work on devices without enrollment (non-managed devices)](./media/app-protection-policies-without-mdm.png)

For BYOD devices not enrolled in any MDM solution, App protection policies can help protect company data at the app level.
However, there are some limitations to be aware of, such as:

- You can't deploy apps to the device. The end user has to get the apps from the store.
- You can't provision certificate profiles on these devices.
- You can't provision company Wi-Fi and VPN settings on these devices.

## Apps you can manage with app protection policies

Any app that has been integrated with the [Intune App SDK](/intune/app-sdk) or wrapped by the [Intune App Wrapping Tool](/intune/apps-prepare-mobile-application-management) can be managed using Intune app protection policies. See the official list of [Microsoft Intune protected apps](apps-supported-intune-apps.md) that have been built using these tools and are available for public use.

The Intune SDK development team actively tests and maintains support for apps built with the native Android, iOS (Obj-C, Swift), Xamarin, Xamarin.Forms, and Cordova platforms. While some customers have had success with Intune SDK integration with other platforms such as React Native and NativeScript, we do not provide explicit guidance or plugins for app developers using anything other than our supported platforms.

The Intune APP SDK uses some advanced modern authentication capabilities from the Azure Active Directory Authentication Libraries (ADAL) for both the 1st party and the 3rd party versions of the SDK. As such, Microsoft Authentication Library (MSAL) does not work well with many of our core scenarios such as authentication into the Intune App Protection service and conditional launch. Given that the overall guidance from Microsoft's Identity team is to switch to MSAL for all of the Microsoft Office apps, the Intune SDK will eventually need to support it, but there are no plans today.

### Requirements to use app protection policies on an Intune-managed app:

- The end user must have an Azure Active Directory (AAD) account. See [Add users and give administrative permission to Intune](/intune/users-permissions-add) to learn how to create Intune users in Azure Active Directory.

- The end user must have a license for Microsoft Intune assigned to their Azure Active Directory account. See [Manage Intune licenses](/intune/licenses-assign) to learn how to assign Intune licenses to end users.

- The end user must belong to a security group that is targeted by an app protection policy. The same app protection policy must target the specific app being used. App protection policies can be created and deployed in the Intune console in the [Azure portal](https://portal.azure.com). Security groups can currently be created in the [Microsoft 365 admin center](https://admin.microsoft.com).

- The end user must sign into the app using their AAD account.

## App protection policies and Microsoft Office apps

### Outlook mobile app
The additional requirements to use the [Outlook mobile app](https://products.office.com/outlook) include the following:

- The end user must have the Outlook mobile app installed to their device.
- The end user must have an [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) mailbox and license linked to their Azure Active Directory account.

  >[!NOTE]
  > The Outlook mobile app currently only supports Intune App Protection for Microsoft Exchange Online and [Exchange Server with hybrid modern authentication](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) and does not support Exchange in Office 365 Dedicated.

### Word, Excel, and PowerPoint
The additional requirements to use the [Word, Excel, and PowerPoint](https://products.office.com/business/office) apps include the following:

- The end user must have a license for [Office 365 Business or Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) linked to their Azure Active Directory account. The subscription must include the Office apps on mobile devices and can include a cloud storage account with [OneDrive for Business](https://onedrive.live.com/about/business/). Office 365 licenses can be assigned in the [Microsoft 365 admin center](https://admin.microsoft.com) following these [instructions](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- The end user must have a managed location configured using the granular save as functionality under the "Prevent Save As" application protection policy setting. For example, if the managed location is OneDrive, the [OneDrive](https://onedrive.live.com/about/) app should be configured in the end user's Word, Excel, or PowerPoint app.

- If the managed location is OneDrive, the app must be targeted by the app protection policy deployed to the end user.

  >[!NOTE]
  > The Office mobile apps currently only support SharePoint Online and not SharePoint on-premises.

### Managed location needed for Office
A managed location (i.e. OneDrive) needed for Office. Intune marks all data in the app as either "corporate" or "personal." Data is considered "corporate" when it originates from a business location. For the Office apps, Intune considers the following as business locations: email (Exchange) or cloud storage (OneDrive app with a OneDrive for Business account).

### Skype for Business
There are additional requirements to use Skype for Business. See [Skype for Business](https://products.office.com/skype-for-business/it-pros) license requirements. For Skype for Business (SfB) hybrid and on-prem configurations, see [Hybrid Modern Auth for SfB and Exchange goes GA](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) and [Modern Auth for SfB OnPrem with AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910), respectively.

## App protection Global policy

If a OneDrive administrator browses to **admin.office.com** and selects **Device** access, they can set **Mobile application management** controls to the OneDrive and SharePoint client apps. 

The settings, made available to the OneDrive Admin console, configure a special Intune app protection policy called the **Global** policy. This global policy applies to all users in your tenant, and has no way to control the policy targeting. 

Once enabled, the OneDrive and SharePoint apps for iOS and Android are protected with the selected settings by default. An IT Pro can edit this policy in the Intune console to add more targeted apps and to modify any policy setting. 

By default, there can only be one **Global** policy per tenant. However, you can use [Intune Graph APIs](intune-graph-apis.md) to create extra global policies per tenant, but doing so isn't recommended. Creating extra global policies isn’t recommended because troubleshooting the implementation of such a policy can become complicated.

While the **Global** policy applies to all users in your tenant, any standard Intune app protection policy will override these settings.

## Examples of app protection policies

To learn more about examples of app protection policies, see the [Android app protection policy settings](app-protection-policy-settings-android.md) and [iOS app protection policy settings](app-protection-policy-settings-ios.md) for detailed information on each app protection policy setting.

## Multi-identity

Multi-identity support allows apps with both "corporate" and consumer audiences (i.e. the Office apps) to be released publicly with Intune app protection capabilities for the "corporate" accounts. Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies apply only when the apps are used in the work context.

For an example of personal context, consider a user who starts a new document in Word, this is considered personal context so Intune App Protection policies are not applied. Once the document is saved on the corporate OneDrive account then it will be considered corporate context and Intune App Protection polices will be applied.

For an example of work context, consider a user who starts the OneDrive app by using their work account. In the work context, they can't move files to a personal storage location. Later, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.

- Learn more about the apps that support [MAM and multi-identity](apps-supported-intune-apps.md) with Intune.

## Next steps

[How to create and deploy app protection policies with Microsoft Intune](app-protection-policies.md)

## See also
Third-party apps such as the Salesforce mobile app work with Intune in specific ways to protect corporate data. To learn more about how the Salesforce app in particular works with Intune (including MDM app configurations settings), see [Salesforce App and Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
