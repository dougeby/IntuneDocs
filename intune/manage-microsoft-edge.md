---
# required metadata

title: Manage web access using Microsoft Edge with Microsoft Intune 
titleSuffix: 
description: Use Intune app protection policies with Microsoft Edge to ensure corporate websites are always accessed with safeguards in place. 
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Manage web access using Microsoft Edge with Microsoft Intune

Using Intune app protection policies with Microsoft Edge can ensure corporate websites are always accessed with safeguards in place. The following Microsoft Edge enterprise features enabled by Intune policies are available. These enterprise features include:

1.	**Dual-Identity** - Users can add both a work account, as well as a personal account, for browsing. There is complete separation between the two identities, which is similar to the architecture and experience in Office 365 and Outlook. Intune admins will be able to set the desired policies for a protected browsing experience within the work account.
2.	**Intune app protection policy integration** – Since Microsoft Edge is integrated with the Intune SDK, you can target app protection policies to ensure data loss protection. These capabilities include the control of cut, copy, and paste, preventing screen captures, and ensuring that user-selected links open only in other managed apps.
3.	**Azure Application Proxy integration** - You can control access to SaaS apps and web apps, helping ensure browser-based apps only run in the secure Microsoft Edge browser, whether end users connect from the corporate network or connect from the Internet.
4.	**Application configuration** – You can leverage application configuration settings to strengthen your organizations security posture and configure ease-of-use features for your end users. For example, you can define bookmarks, a homepage shortcut, allowed/blocked sites, Azure Application Proxy, and more.
Microsoft Intune protection policies for Microsoft Edge help to protect your organization’s data and resources. Using these policies with Microsoft Edge ensures that your company’s resources are protected not only within natively installed apps, but also when accessed through the web browser.

## Getting started

You and your end users can download Microsoft Edge from public app stores for use in your organizations. 
Operating system requirements for browser policies:
- Android 4 and later, or
- iOS 8.0 and later

## Application protection policies for Microsoft Edge

Because Microsoft Edge is integrated with the Intune SDK, you can apply application protection policies to them, including:
- Controlling the use of cut, copy, and paste.
- Preventing screen captures.
- Ensuring corporate links open only within managed apps and browsers.

For details, see What are app protection policies?
You can apply these settings to:
- Devices that are enrolled with Intune
- Enrolled with another MDM product
- Unmanaged devices

If Microsoft Edge is not targeted with Intune policy, users cannot use it to access data from other Intune-managed applications such as Office apps. 

## Conditional Access for Microsoft Edge

You can leverage Azure AD Conditional Access to redirect your users to access corporate content only through Microsoft Edge. This would restrict mobile browser access to Azure AD-connected web apps to policy-protected Microsoft Edge, and this would block access from any other unprotected browsers such as Safari or Chrome. Conditional access can be applied to Azure resources like Exchange Online and SharePoint Online, the Microsoft 365 admin center, and even on-premises sites that you have exposed to external users via the [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

To restrict Azure AD-connected web apps to use Microsoft Edge on iOS and Android, follow the below steps:
1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Under the Intune node, select **Conditional access** > **New policy**.
3. Next, select **Grant** from the **Access controls** section of the blade.
4. Click **Require approved client app**.
5. Click **Select** on the **Grant** blade. This policy must be assigned to the cloud apps that you want to be accessible to only the Intune Managed Browser app.

    ![Conditional access policy - Grant](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. In the Assignments section, select Conditions > Client apps. The Client apps blade is displayed.
7. Click Yes under Configure to apply the policy to specific client apps.
8. Verify that Browser is selected as a client app.

    ![Conditional access policy - Select client apps](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > If you want to restrict which native apps (non-browser apps) can access these cloud applications, you can also select **Mobile apps and desktop clients**.

9. In the **Assignments** section, select **Users and groups** and then choose the users or groups you would like to assign this policy.

    > [!NOTE]
    > Users must also be targeted with Intune App Protection policy in order to receive App Configuration policies. For more information about creating Intune App Protection policies, see [What are app protection policies?](app-protection-policy.md)

10. In the **Assignments** section, select **Cloud apps** to choose which apps to protect with this policy.

Once the above policy is configured, users will be forced to use Microsoft Edge to access the Azure AD-connected web apps you have protected with this policy. If users attempt to use an unmanaged browser in this scenario, they will see a message that they must use Microsoft Edge.

> [!TIP]
> Conditional Access is an Azure Active Directory (Azure AD) technology. The Conditional Access node accessed from Intune is the same node as accessed from Azure AD.

## Single Sign-on to Azure AD-connected web apps in policy-protected browsers

Microsoft Edge on iOS and Android can take advantage of SSO to all web apps (SaaS and on-prem) that are Azure AD-connected. SSO allows users to access Azure AD-connected web apps through Microsoft Edge without having to re-enter their credentials.

SSO requires your device to be registered by either the Microsoft Authenticator app for iOS devices, or the Intune Company Portal on Android. When users have the Authenticator app or Intune Company Portal, they will be prompted to register their device when they navigate to an Azure AD-connected web app in a policy-protected browser, if their device has not already been registered yet. Once the device is registered with the user’s account managed by Intune, that account will have SSO enabled for Azure AD-connected web apps.

> [!NOTE]
> Device registration is a simple check-in with the Azure AD service. It does not require full device enrollment and does not give IT any additional privileges on the device.

## Create a protected browser app configuration

For app configurations to apply, the user's protected browser or another app on the device must already be managed by [Intune app protection policy](app-protection-policy.md).

The following steps are used to create a protected browser app configuration:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Select **Client apps** > **App configuration policies** > **Add**.
3. On the **Add configuration policy** blade, enter a **Name** and optional **Description** for the app configuration settings.
4. For **Device enrollment** type, choose **Managed apps**.
5. Choose **Select the required app** and then, on the **Targeted apps** blade, choose the **Managed Browser** and/or **Edge** for iOS, for Android, or for both.
6. Choose **OK** to return to the **Add configuration policy** blade.
7. Choose **Configuration settings**. On the **Configuration** blade, you define key and value pairs to supply configurations for Microsoft Edge. Use the sections later in this article to learn about the different key and value pairs you can define.

    > [!NOTE]
    > Microsoft Edge uses the same key and value pairs as the Managed Browser. 

8.	When you are done, click **OK**.
9.	On the **Add configuration policy** blade, choose **Add**.<br>
	The new configuration is created and displayed on the **App configuration** blade.

## Assign the configuration settings you created 

You assign the settings to Azure AD groups of users. If that user has the targeted protected browser app installed, then the app is managed by the settings you specified.

1. On the **Client apps** blade of the Intune mobile application management dashboard, choose **App configuration policies**.
2. From the list of app configurations, select the one you want to assign.
3. On the next blade, choose **Assignments**.
4. On the **Assignments** blade, select the Azure AD group to which you want to assign the app configuration, and then choose **OK**.

## How to configure Application Proxy settings for protected browsers

Microsoft Edge and [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) can be used together to give users access to intranet sites on their mobile devices. 

These are some examples of the scenarios AD Application Proxy enable: 

- A user is using the Outlook mobile app, which is protected by Intune. They then click a link to an intranet site in an email, and Microsoft Edge recognizes that this intranet site has been exposed to the user through the Application Proxy. The user is automatically routed through the Application Proxy, to authenticate with any applicable multi-factor authentication and conditional access before reaching the intranet site. Users are now able to access internal sites even on their mobile devices, and the link in Outlook works as expected.
- A user opens Microsoft Edge on their iOS or Android device. If Microsoft Edge is protected with Intune, and Application proxy is enabled, the user can navigate to an intranet site using the internal URL they are used to. Microsoft Edge recognizes that this intranet site has been exposed to the user via the Application Proxy, and the user is automatically routed through the Application Proxy, to authenticate before reaching the intranet site. 

### Before you start

- Set up your internal applications through the Azure AD Application Proxy.
    - To configure Application Proxy and publish applications, see the [setup documentation](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Microsoft Edge app must have [Intune app protection policy](app-protection-policy.md) assigned.

> [!NOTE]
> Updated Application Proxy redirection data can take up to 24 hours to take effect in the Managed Browser and Microsoft Edge.

#### Step 1: Enable automatic redirection to a protected browser from Outlook
Outlook must be configured with an app protection policy that enables the setting **Share web content with policy managed browsers**.

![App protection policy - Share web content with policy managed browsers](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### Step 2: Set the app configuration setting to enable app proxy
Target Microsoft Edge with the below key/value pair to enable application proxy for Microsoft Edge:

|    Key    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true    |

For more information about how Microsoft Edge and Azure AD Application Proxy can be used in tandem for seamless (and protected) access to on-premises web apps, see the Enterprise Mobility + Security blog post [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). This blog post references the Intune Managed Browser, but the content applies to Microsoft Edge as well.

## How to configure a homepage shortcut for Microsoft Edge

This setting allows you to configure a homepage shortcut for Microsoft Edge.  The homepage shortcut you configure will appear as the first icon beneath the search bar when they open a new tab in Microsoft Edge. The user will not be able to edit or delete this shortcut in their managed context. The homepage shortcut will display your organization's name to distinguish it. 

Use the below key/value pair to configure a homepage shortcut:

|    Key    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Specify a valid URL. Incorrect URLs are blocked as a security measure.<br>**Example:** `<https://www.bing.com`>
    |

## How to configure managed bookmarks for Microsoft Edge

For ease of access, you can configure bookmarks that you’d like your users to have available when they are using Microsoft Edge. 
Here are some details:

- These bookmarks will only appear for users when they are using the corporate mode of Microsoft Edge. 
- These bookmarks cannot be deleted or modified by users.
- These bookmarks display at the top of the list. Any bookmarks that users create are displayed below these bookmarks.
- If you have enabled App Proxy redirection, you can add App Proxy web apps using either their internal or external URL.

Use the following key/value pair to configure managed bookmarks:

|    Key    |    Value    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    The value for this configuration is a   list of bookmarks. Each bookmark consists of the bookmark title, and the   bookmark URL. Separate the title, and URL with the `|` character.      **Example:**<br>`Microsoft Bing|https://www.bing.com`<p>To configure multiple bookmarks, separate each pair with the double character `||`.<p>**Example:**<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## How to display MyApps within Microsoft Edge bookmarks

By default, your users will be shown the MyApps sites that are configured to them within a folder inside Microsoft Edge bookmarks. The folder will be labeled with the name of your organization.

|    Key    |    Value    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **True** shows MyApps within the Microsoft Edge bookmarks.<p>**False** hides MyApps within Microsoft Edge.    |

## How to specify allowed or blocked sites list for Microsoft Edge
You can use app configuration to define which sites your users can access when using their work profile. If you use an allow list, your users will only be able to access the sites you’ve explicitly listed. If you use a blocked list, your users will be able to access all sites except for the sites you’ve explicitly blocked. You should only impose either an allowed or block list, not both. If both are targeted to the device, the allowed list will be honored.  

You can use the below key/value pairs to configure either an allowed or blocked site list for Microsoft Edge. Continue reading for more info about valid URL formats. 

|    Key    |    Value    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Choose from:<p>1. Specify allowed URLs (only these URLs are allowed; no other sites can be accessed):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Specify blocked URLs (all other sites can be accessed):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    The corresponding value for the key is a list of URLs. You enter all the URLs you want to allow or block as a single value, separated by a pipe `|` character.<p>**Examples:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### URL formats for allowed and blocked site list 
You can use various URL formats to build your allowed/blocked sites lists. These permitted patterns are detailed in the table below. Some notes before you get started: 
- Ensure that you prefix all URLs with **http** or **https** when entering them into the list.
- You can use the wildcard symbol (*) according to the rules in the following permitted patterns list.
- A wildcard can only match an entire compoment of the hostname (spearated by periods) or entire parts of the path (separated by forward slashes). For example, `http://*contoso.com` is **not** supported.
- You can specify port numbers in the address. If you do not specify a port number, the values used are:
    - Port 80 for http
    - Port 443 for https
- Using wildcards for the port number is **not** supported. For example, `http://www.contoso.com:*` and `http://www.contoso.com:*/` are not supported. 

    |    URL    |    Details    |    Matches    |    Does not match    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Matches a single page    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Matches a single page    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/&#42;`   |    Matches all URLs that begin with `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Matches all subdomains under `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`    |
    |    `http://www.contoso.com/images`    |    Matches a single folder    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Matches a single page, by using a port   number    |    http://www.contoso.com:80    |         |
    |    `https://www.contoso.com`    |    Matches a single, secure page    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Matches a single folder and all subfolders    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- The following are examples of some of the inputs that you cannot specify:
    - `*.com`
    - `*.contoso/*`
    - `www.contoso.com/*images`
    - `www.contoso.com/*images*pigs`
    - `www.contoso.com/page*`
    - IP addresses
    - `https://*`
    - `http://*`
    - `https://*contoso.com`
    - `http://www.contoso.com:*`
    - `http://www.contoso.com: /*`
  
## Defining behavior when users try to access a blocked site

With the dual-identity model built into Microsoft Edge, you can enable a more flexible experience for your end users that was not possible with the Intune Managed Browser. When users hit a blocked site in Microsoft Edge, they can be prompted to open the link in their personal context instead of their work context, which enables them to stay protected, while keeping corporate resources safe. For example, if a user is sent a link to a news article through their Outlook, they will be able to open the link in their personal context or in an InPrivate tab instead of their work context, which does not allow news websites. By default, these transitions are allowed.

Use the below key/value pair to configure if these soft transitions are allowed:

|    Key    |    Value    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **True** allows Microsoft Edge to transition users to their   personal context to open blocked sites<p>**Block** prevents Microsoft Edge from transitioning users,   and users will simply be shown a message stating the site they are trying to   access is blocked.    |

## Directing users to Microsoft Edge instead of the Intune Managed Browser 

Both the Intune Managed Browser and Microsoft Edge are now can be used as policy-protected browsers. To ensure that your users are being directed to use the correct browser app, target all of your Intune-managed apps (e.g. Outlook and OneDrive) with the following configuration setting:

|    Key    |    Value    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    The value `true` will direct your users to use Microsoft Edge.<p>The value `false` will direct your users to use the Intune Managed Browser.    |

If this app configuration value is not set, the following logic will define which browser will be used to open corporate links.

On Android:
- The Intune Managed Browser will launch if a user has both the Intune Managed Browser and Microsoft Edge downloaded on their device. 
- Microsoft Edge will open if only Microsoft Edge is downloaded on the device and is targeted with Intune policy.
- Managed Browser will open if only Managed Browser is on the device and is targeted with Intune policy.

On iOS, for apps that have integrated the Intune SDK for iOS v. 9.0.9+:
- The Intune Managed Browser will launch if both the Managed Browser and Microsoft Edge are on the device.  
- Microsoft Edge will launch if only Microsoft Edge is on the device and is targeted with Intune policy.
- Managed Browser if only Managed Browser is on the device and is targeted with Intune policy.

## Using Microsoft Edge on iOS to access managed app logs 

End users with Microsoft Edge installed on their iOS device can view the management status of all Microsoft published apps. They can send logs for troubleshooting their managed iOS apps.
1. Open Microsoft Edge on your iOS device.
2. Type `about:intunehelp` in the address box. 
3. Troubleshooting mode will be launched from within Microsoft Edge.

For a list of the settings stored in the app logs, see [Review app protection logs in the Managed Browser](app-protection-policy-settings-log.md).

To see how to view logs on Android devices, see [Send logs to your IT admin by email](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## Security and privacy for Microsoft Edge

Additional security and privacy considerations for Microsoft Edge:

- Microsoft Edge does not consume settings that users set for the native browser on their devices, because Microsoft Edge cannot access to these settings.
- If you configure the option **Require simple PIN for access** or **Require corporate credentials for access** in an app protection policy associated with Microsoft Edge, and a user selects the help link on the authentication page, they can browse any Internet sites regardless of whether they were added to a block list in the policy.
- Microsoft Edge can block access to sites only when they are accessed directly. It does not block access when intermediate services (such as a translation service) are used to access the site.
- To allow authentication, and access to Intune documentation, ***.microsoft.com** is exempt from the allow or block list settings. It is always allowed.
Turn off usage data
Microsoft automatically collects anonymous data about the performance and use of the Managed Browser to improve Microsoft products and services. Users can turn off data collection by using the **Usage Data** setting on their devices. You have no control over the collection of this data. On iOS devices, websites that users visit that have an expired or untrusted certificate cannot be opened.

## Next steps

- [What are app protection policies?](app-protection-policy.md) 
