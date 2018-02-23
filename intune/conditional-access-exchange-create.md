---
# required metadata

title: Create and assign on-premises Exchange conditional access policy
titlesuffix: "Azure portal"
description: "Configure conditional access for Exchange on-premises and legacy Exchange Online Dedicated in Intune."
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 02/14/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create and assign a conditional access policy for Exchange on-premises and legacy Exchange Online Dedicated in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic walks you through the process of configuring conditional access for Exchange on-premises based on device compliance.

If you have an Exchange Online Dedicated environment and need to find out whether it is in the new or the legacy configuration, please contact your account manager. To control email access to Exchange on-premises or to your legacy Exchange Online Dedicated environment, configure conditional access to Exchange on-premises in Intune.

## Before you begin

Before you can configure conditional access, verify the following:

- Your Exchange version must be **Exchange 2010 SP1 or later**. Exchange server Client Access Server (CAS) array is supported.

- You must use the [Exchange Active Sync on-premises Exchange connector](exchange-connector-install.md), which connects Intune to on-premises Exchange.

	>[!IMPORTANT]
	>The on-premises Exchange connector is specific to your Intune tenant and cannot be used with any other tenant. You should also ensure that the exchange connector for your tenant is installed **on only one machine**.

- The connector can be installed on any machine as long as that machine is able to communicate with the Exchange server.

- The connector supports **Exchange CAS environment**. You can technically install the connector on the Exchange CAS server directly if you wish to, but it is not recommended, as it will increase the load on the server. When configuring the connector, you must set it up to communicate to one of the Exchange CAS servers.

- **Exchange ActiveSync** must be configured with certificate based authentication, or user credential entry.

- When conditional access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:
	- Either **enrolled** with Intune or is a domain joined PC.
	- **Registered in Azure Active Directory**. Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.
<br></br>
- AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory. **This does not apply to Windows PCs and Windows Phone devices**.

- **Compliant** with device compliance policies deployed to that device.

- If the device does not meet conditional access settings, the user is presented with one of the following messages when they log in:
	- If the device is not enrolled with Intune, or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email. This process also associates the device's Exchange ActiveSync ID with the device record in Azure Active Directory.
	- If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website, or the Company Portal app where they can find information about the problem and how to remediate it.

### Support for mobile devices

- Windows Phone 8.1 and later
- Native email app on iOS.
- EAS mail clients such as Gmail on Android 4 or later.
- EAS mail clients **Android for Work devices:** Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices. For conditional access to work with Android for Work, you must deploy an email profile for the Gmail or Nine Work app, and also deploy those apps as a required install.

> [!NOTE]
> Microsoft Outlook app for Android and iOS is not supported. 

### Support for PCs

The native **Mail** application on Windows 8.1 and later (when enrolled with Intune)


## Configure Exchange on-premises access

1. Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.

2. After you've successfully signed in, you see the **Azure Dashboard**.

3. Choose **More services** from the left menu, then type **Intune** in the text box filter.

4. Choose **Intune**, you see the **Intune Dashboard**.

5. Choose **On-Premise Access**, then choose

6. The **On-premises** blade shows the status of the conditional access policy and the devices that are affected by it.

7. Under **Manage**, choose **Exchange on-premises access**.

8. On the **Exchange on-premises access** blade, choose **Yes** to enable Exchange on-premises access control.

  	> [!NOTE]
  	> If you have not configured the Exchange Active Sync on-premises connector, this option will be disabled.  You must first install and configure this connector before enabling conditional access for Exchange on-premises. For more details, see [Install the Intune On-premises Exchange Connector](exchange-connector-install.md)

9. Under **Assignment**, choose **Groups Included**.  Use the security user group that should have conditional access applied to it. This would require the users to enroll their devices in Intune and be compliant with the compliance profiles.

10. If you want to exclude a certain groups of users, you can do so by choosing **Groups Excluded** and selecting a user group that you want to be exempt from requiring device enrollment and compliance.

11. Under **Settings**, choose **User notifications** to modify the default email message. This message is sent to users if their device is not compliant and they want to access Exchange on-premises. The message template uses Markup language.  You will also see the preview of how the message looks as you type.
	> [!TIP]
	> To learn more about Markup language see this Wikipedia [article](https://en.wikipedia.org/wiki/Markup_language).

12. On the **Advanced Exchange Active Sync access settings** blade, set the global default rule for access from devices that are not managed by Intune, and for platform-level rules as described in the next two steps.

13. For a device that is not affected by conditional access or other rules, you can choose to allow it to access Exchange, or block it.
  - When you set this to allow access, all devices will be able to access Exchange on-premises immediately.  Devices that belong to the users in the **Groups Included**, are blocked if they are subsequently evaluated as not compliant with the compliant policies or not enrolled in Intune.
  - When you set this to block access, all devices will be immediately blocked from accessing Exchange on-premises initially.  Devices that belong to users in the **Groups Included** will get access once the device is enrolled in Intune and is evaluated as compliant. On Android devices that do not run Samsung Knox standard will always be blocked as they do not support this setting.
<br></br>
14. Under **Device platform exceptions**, choose **Add** to specify the platforms. If the **unmanaged device access** setting is set to **blocked**, devices that are enrolled and compliant will be allowed even if there is a platform exception to block. Choose **Ok** to save the settings.

15. On the **On-premises** blade, click **Save** to save the conditional access policy.

## Create Azure AD Conditional access policies in Intune

Beginning with Intune 1704 release, admins can create Azure AD conditional access policies from the Intune Azure portal, which gives convenience so you don't need to switch between the Azure and Intune workloads.

> [!IMPORTANT]
> You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.

### To create Azure AD conditional access policy

1. In the **Intune Dashboard**, choose **Conditional access**.

2. In the **Policies** blade, choose **New policy** to create your new Azure AD conditional access policy.

## See also

[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
