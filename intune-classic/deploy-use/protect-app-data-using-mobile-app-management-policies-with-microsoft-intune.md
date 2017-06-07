---
# required metadata

title: Protect app data using MAM policies 
description: This topic explains how mobile application management policies can help protect your company data, prevent data loss, and keep personal and work information separate.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Protect app data using app protection policies with Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## How you can protect app data
Your employees use mobile devices for both personal and work tasks. While you're making sure your employees can be productive, you also want to prevent data loss—intentional and unintentional.  In addition, you want to have the ability to protect company data that employees access by using devices that you don't manage.

You can use Intune app protection policies to help protect your company’s data. Because Intune App protection policies can be used **independent of any mobile device management (MDM) solution**, you can use MAM to protect your company’s data with or without enrolling devices in a device management solution. By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.

You can configure app protection policies for apps running on devices that are:

-   **Enrolled in Microsoft Intune:** The devices in this category are typically corporate-owned devices.

-   **Enrolled in a third-party MDM solution:** The devices in this category are typically corporate-owned devices.

  	> [!NOTE]
  	> We don't recommend using app protection policies with third-party mobile application management or secure container solutions.

-   **Not enrolled in any MDM solution:** The devices in this category are typically employee-owned devices that are not managed or enrolled in Intune or other MDM solutions.

> [!IMPORTANT]
> You can create app protection policies for Office mobile apps that connect to Office 365 services. App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.

## Benefits of using app protection policies

-   **They help protect your company data at the app level.** Because mobile application management doesn't require device management, you can protect company data on both managed and unmanaged devices. The management is centered on the user identity, which removes the requirement for device management.

-   **User productivity is not impacted, and the policies aren't applied when you're using the app in a personal context.** The policies are applied only in a work context, which gives you the ability to protect company data without touching personal data.

There are additional benefits to using MDM with app protection policies, and companies can use MAM with and without MDM at the same time. For example, an employee might use a company-issued phone, as well as a personal tablet. In this case, the company phone is enrolled in MDM and protected by app protection policies, and the personal device is protected by app protection policies only.

- **MDM makes sure that the device is protected.** For example, you can require a PIN to access the device, or you can deploy managed apps to the device. You can also deploy apps to devices through your MDM solution to give you more control over app management.

- **App protection policies make sure that the app-layer protections are in place.** For example, you can have a policy that requires a PIN to open an app in a work context, prevents data from being shared between apps, and prevents company app data from being saved to a personal storage location.

## Devices that support MAM
App protection policies are currently supported on:
-   iOS 8.1 or later
-   Android 4 or later

>[!NOTE]
>Windows devices are not supported in the MAM without enrollment scenario. However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality. For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


##  How app protection policies protect app data

###  Apps without app protection policies

![Image that shows how data can move freely between apps when there are no app protection policies in place](../media/Apps_without_MAM_policies.png)

When you use apps without restrictions, company and personal data can get intermingled. Company data might end up in locations like personal storage or might be transferred to apps outside of your purview, which could result in data loss. The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.

### Data protection with app protection policies

![Image that shows how company data is protected when app protection policies are applied](../media/Apps_with_mobile_app_policies.png)

You can use app protection policies to prevent company data from saving to the local storage of the device, and to restrict data movement to other apps that aren't protected by app protection policies. App protection policy settings include:
- Data relocation policies like
 **Prevent Save As** and **Restrict cut, copy, and paste**.
- Access policy settings like **Require simple PIN for access** and **Block managed apps from running on jailbroken or rooted devices**.

### Data protection with app protection on devices that are managed by a MDM solution

![Image that shows how app protection policies work on Bring Your Own Devices (BYOD) devices](../media/MAM_BYOD_November.png)

**For devices enrolled in an MDM solution**: The preceding diagram shows the layers of protection that MDM and app protection policies offer together.

The MDM solution:

-   Enrolls the device.

-   Deploys apps to the device.

-   Provides ongoing device compliance and management.

**App protection policies add value because they:**

-   Help protect company data from leaking to consumer apps and services.

-   Apply restrictions (save-as, clipboard, PIN, etc.) to mobile apps.

-   Wipe company data from apps without removing those apps from the device.


### Data protection with app protection policies for devices without enrollment

![Image that shows how app protection policies work on managed devices](../media/MAM_ManagedDevices_November.png)

The preceding diagram illustrates how data protection policies work at the app level without MDM.

For BYOD devices that aren't enrolled in any MDM solution, app protection policies can help protect company data at the app level.

However, there are some limitations to be aware of:

-   You can't deploy apps to the device. The user has to get the apps from the store.

-   You can't provision certificate profiles on these devices.

-   You can't set up company Wi-Fi and VPN settings on these devices.


## Multi-identity

Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.  

For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location. However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.  

- Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.

##  Next steps
- [Get ready to configure app protection policies](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Create and deploy app protection policies with Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
