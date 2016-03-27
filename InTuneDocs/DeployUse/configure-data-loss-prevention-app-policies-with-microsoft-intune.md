---
title: Introduction to mobile app management policies |Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
author: karthikaraman
---
# Introduction to mobile app management policies with Microsoft Intune
Use mobile app management policies in [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] to apply restrictions to apps that help protect your company data.

## How you can protect app data
Your employees use mobile devices for both personal and work tasks.  While making sure your employees can be productive, you also want to prevent data loss, intentional and unintentional.  Moreover, you want to be able to protect data on devices whether or not your company manages them.

You can use mobile app management (MAM) policies to help protect your company’s data . Because this capability is **independent of any mobile-device management solution**, you can use it to protect your company’s data with or without enrolling devices in a device management solution. By simply implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.

MAM policies support the following scenarios:

-   **Devices that are managed and enrolled** in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].  These are typically corporate owned devices that  you manage.

    > [!IMPORTANT]
    > If you are using Intune with Configuration Manager to manage your iOS and Android devices, you can create mobile app management policies for Office mobile apps that connect to Office 365 services, This is not supported for apps that connect to on-premises Exchange or SharePoint services.

-   **Devices that are managed and enrolled in a third party mobile device management** (referred to as **MDM** from here on) solution.   These are typically corporate owned devices that you manage.

    > [!NOTE]
    > Mobile app management policies should not be used with third party mobile app management  or secure container solutions.

-   **Devices that are not managed**.  These are typically employee owned devices that are not enrolled or managed using an MDM solution.

> [!IMPORTANT]
> There are additional benefits to using MDM with MAM  policies, and companies can use both at the same time. For example, an employee may use a phone issued by the company as well as a personal tablet.  In this case, the company phone is enrolled in MDM and protected by MAM policies, and the personal device is protected by MAM policies only.

**MDM makes sure that the device is protected**.  For example, you can require a PIN to access the device, or you can deploy managed apps to the device. You can also deploy apps to devices through your MDM solution, to give you more control over app management.

**MAM policies makes sure that the app-layer protections are in place**. For example, you can require a PIN to open an app in a work context, or if data can be shared between apps, or preventing company app data from being saved to a personal storage location.

**The key benefits of using MAM policies are:**

-   Protecting your company data at the app level.  Since mobile app management does not require device management, you can protect company data on both managed and unmanaged devices. Data management is centered around user identity which removes the requirement for device management.

-   End-user productivity is not impacted, and the policies are not applied when using the app in a personal context.  The policies are applied only in a work context, thus giving you the ability to protect company data without touching personal data.

### MAM polices are currently supported on:
-   iOS 8.1 or later

-   Android 4 or later

##  How MAM policies protect app data

####  Apps without MAM policies:

![](../media/Apps_without_MAM_policies.png)

When apps are used without restrictions, company and personal data can get intermingled.  Company data could end up in locations like personal storage or transferred to apps outside of your  purview,  resulting in data loss. The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.

### Data protection with MAM policies:

![](../media/Apps_with_mobile_app_policies.png)

You can use MAM policies to prevent company data from saving to the local storage of the device, and restrict data movement to other apps that are not protected by MAM policies. MAM policy settings include:
- Data relocation policies like:
 **Prevent Save As**, **Restrict cut, copy, and paste**.
- Access policy settings like **Require simple PIN for access**, **Block managed apps from running on jailbroken or rooted devices**.

### Data protection with MAM policies on devices managed by a MDM solution:

![](../media/MAM_BYOD_November.png)

**For devices enrolled in an MDM solution**-

The illustration above shows the layers of protection that MDM and MAM policies offer together.

The MDM solution:

-   Enrolls the device

-   Deploys the apps to the device

-   Provides ongoing device compliance and management

**MAM policies add value by:**

-   Helping protect  company data from leaking to consumer apps and services

-   Applying restrictions (save-as, clipboard, PIN, etc.) to mobile apps

-   Wipe company data from apps without removing those apps from the device


### Data protection with MAM policies for devices without enrollment

![](../media/MAM_ManagedDevices_November.png)

The diagram above illustrates how the data protection policies work at the app level without MDM.

For BYOD devices not enrolled in any MDM solution, MAM policies can help protect company data at the app level.
However, there are some limitations to be aware of, like:

-   You cannot deploy apps to the device.  The end-user has to get the apps from the store.

-   You cannot provision certificate profiles on these devices.

-   You cannot provision company Wi-Fi and VPN settings on these devices.


## Multi-identity

Apps that support multi-identity gives you the ability to use different accounts - work and personal, to access the same apps while MAM policies are applied on when the apps are used in the work context.  

For example, when the end-user launches the OneDrive app using their the work account, they are prevented from copying the content from a word document stored in the company location to a personal storage or use it with their twitter account. When the end-user uses OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.

For a detailed explanation of the experience of using apps that are associated with MAM policies, and how apps with Multi-identity support enable applying MAM policies only in work context, read [End-user experience for apps associated with Microsoft Intune mobile app management policies](end-user-experience-for-apps-associated-with-microsoft-intune-mobile-app-management-policies.md)

All Office mobile apps support multi-identity.

##  Next Steps
[Get started with mobile app management policies in the Azure portal](../Topic/Get-started-with-mobile-app-management-policies-in-the-Azure-portal.md)

[Create and deploy mobile app management policies with Microsoft Intune](../Topic/Create-and-deploy-mobile-app-management-policies-with-Microsoft-Intune.md)
