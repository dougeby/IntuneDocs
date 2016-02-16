---
title: Configure data loss prevention app policies with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
author: karthikaraman
---
# Configure data loss prevention app policies with Microsoft Intune
Use mobile app management policies in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] to apply restrictions to apps that help protect your company data.

**In this topic**

[How you can protect app data](#bkmk_protectdata)

[How MAM policies protect app data](#bkmk_howMAMworks)

[How you can configure MAM policies.](#bkmk_WaystoConfigure)

[Next Steps](#bkmk_nextsteps)

### <a name="bkmk_protectdata"></a>How you can protect app data
Your employees use mobile devices for both personal and work tasks.  While making sure your employees can be productive, you also want to prevent data loss, intentional and unintentional.  Moreover, you want to be able to protect data on devices whether or not your company manages them.

You can use mobile app management (MAM) policies to help protect your company’s data . Because this capability is **independent of any mobile-device management solution**, you can use it to protect your company’s data with or without enrolling devices in a device management solution. By simply implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.

MAM policies support the following scenarios:

-   **Devices that are managed and enrolled** in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].  These are typically corporate owned devices that  you manage.

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

### <a name="bkmk_howMAMworks"></a>How MAM policies protect app data
The following diagrams illustrate how MAM works to protect company data in apps.

![](../Image/Apps_without_MAM_policies.png)

As shown in **Figure 1**, when apps are used without restrictions, company and personal data can get intermingled.  Company data could end up in locations like personal storage or transferred to apps outside of your  purview,  resulting in data loss. The diagram below illustrates the state without any restrictions. The arrows show data movement between apps (corporate and personal) and to storage locations.

![](../Image/Apps_with_MAM_policies.png)

Figure 2 represents the same environment but with the policies in place restricting data sharing.  With the data protection policies, you can configure policies that prevent company data from saving to the local storage of the device, or move between apps not protected by the data protection policies. These policies allow you to set various data relocation and access policies that help keep company data secure. 
However, the policies do not take effect when the end-user uses the app to do personal work, since the restrictions are only seen in the work context.  This allows the end-user of the device to use the app for both personal and work tasks. We call this multi-identity support.

**Multi-identity:**

Multi-identity gives you the ability to use different accounts - work and personal, to access the same apps.  On devices where apps are used both for personal and work tasks, you want to apply the policy when the end-user is using the app with their work account, but not when they are using it with their personal account.  [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] MAM policies do just that.  The restrictions apply only when the user signs into an app using the work account. When the user signs into the same app with their personal account, the policy settings are not enforced and the user is free to move data without restrictions.

All Office mobile apps support multi-identity.

Read [End-user experience for apps associated with Microsoft Intune mobile app management policies](../Topic/End-user-experience-for-apps-associated-with-Microsoft-Intune-mobile-app-management-policies.md) topic to understand how and the MAM policies affect the end-user experience.

**Devices managed by a MDM solution**

![](../Image/MAM_ManagedDevices_November.png)

**For devices enrolled in an MDM solution**-

The MDM solution:

-   Enrolls the device

-   Deploys the apps to the device

-   Provides ongoing device compliance and management

**MAM policies add value by:**

-   Helping protect  company data from leaking to consumer apps and services

-   Applying restrictions (save-as, clipboard, PIN, etc.) to mobile apps

-   Wipe company data from apps without removing those apps from the device

Figure 3 shows the layers of protection that MDM and MAM policies offer.

**Unmanaged BYOD devices**

![](../Image/MAM_BYOD_November.png)

For BYOD devices not enrolled in any MDM solution, MAM policies can help protect company data at the app level. There are some limitations to be aware of, like:

-   You cannot deploy apps to the device.  The end-user has to get the apps from the store.

-   You cannot provision certificate profiles on these devices.

-   You cannot provision company Wi-Fi and VPN settings on these devices.

Figure 4 shows how the data protection policies work at the app level without MDM.

### <a name="bkmk_WaystoConfigure"></a>How you can configure MAM policies.
You can configure MAM policies in the following two ways:

1.  You can use the **Azure preview portal** to configure policies and deploy them to users.  You can use this portal to configure policies in three scenarios:

    -   Devices not managed by any mobile device management solution.

    -   Devices enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or a third party MDM. You can create MAM policies and deploy the apps to users in this portal. The end-users will have to download the apps from Apple store or Google Play.  If you want to deploy apps to devices with the MAM policies, use the **Intune admin console**. See [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md) for more details.

        > [!IMPORTANT]
        > If you are using Intune with Configuration Manager to manage your iOS and Android devices, you can create mobile app management policies for Office mobile apps that connect to Office 365 services.  This is not supported for apps that connect to on-premises Exchange or SharePoint services.

    Read the [Get started with mobile app management policies in the Azure portal](../Topic/Get-started-with-mobile-app-management-policies-in-the-Azure-portal.md) for more details on how to use the Azure preview portal.

2.  The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console only supports configuring MAM policies for devices that are enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    Find out how to [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md).

### <a name="bkmk_nextsteps"></a>Next Steps
[Get started with mobile app management policies in the Azure portal](../Topic/Get-started-with-mobile-app-management-policies-in-the-Azure-portal.md)

[Create and deploy mobile app management policies with Microsoft Intune](../Topic/Create-and-deploy-mobile-app-management-policies-with-Microsoft-Intune.md)

## See Also
[Configure apps](../Topic/Configure-apps.md)
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md)

