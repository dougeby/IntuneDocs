---
# required metadata

title: Tutorial - Walkthough Intune in the Azure portal
titleSuffix: Microsoft Intune
description: In this tutorial, you will tour Microsoft Intune to better understand how to accomplish tasks.
keywords:
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 01/22/2018
ms.topic: tutorial
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Tutorial: Walkthough Microsoft Intune in the Azure portal

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) contains over a 100 services to assist you with a variety of cloud computing scenarios and possibilities. Microsoft Intune is one of several services available in Azure. Intune helps you ensure that your company's devices, apps and data meet your company's security requirements. You have the control to set which requirements need to be checked and what happens when those requirements aren't met. The [Azure portal](https://portal.azure.com) is where you can find the Microsoft Intune service. Understanding the features available in Intune will help you accomplish various Mobile Device Management (MDM) and Mobile Application Management (MAM) tasks.

In this tutorial, you will:
> [!div class="checklist"]
> * Tour Microsoft Intune
> * Configure the Azure portal

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Prerequisites
Before setting up Microsoft Intune, review the following requirements:

   - [Supported operating systems and browsers](supported-devices-browsers.md) 
   - [Network configuration requirements and bandwidth](network-bandwidth-use.md)

## Sign up for a Microsoft Intune free trial

Trying out Intune is free for 30 days. If you already have a work or school account, **sign in** with that account and add Intune to your subscription. Otherwise, you can [sign up for a free trial account](free-trial-sign-up.md) to use Intune for your organization.

> [!IMPORTANT]
> You can't combine an existing work or school account after you sign up for a new account.

## Tour Microsoft Intune

Follow the steps below to better understand Intune in the Azure portal. Once you complete the tour, you'll have a better understanding of some of the major areas of Intune.

1. Open a browser and sign in to the [Intune portal](https://aka.ms/intuneportal). If you are new to Intune, use your free trial subscription.

    ![Screenshot of the Microsoft Intune portal](media/tutorial-walkthough-intune-portal-01.png)

    When you open Intune or any other service in Azure, the service is displayed in a pane. Some of the first workloads you use in Intune, like **Devices**, **Client apps**, **Users**, and **Groups**, all appear in a full screen pane. A workload is simply a sub-area of a services. When you select the workload, it opens that pane in the full page. Other panes slide out from the right side of the pane when they open, and close to reveal the previous pane. A pane is also referred to as a blade. 

    By default, when you open Intune you'll see the **Overview** pane. This pane provides an overall visual snapshot of device assignment and compliance status, as well as app installation status.

2. From the [Intune](https://aka.ms/intuneportal) overview pane, select **Device enrollment** to display details about the enrolled devices in your Intune tenant. If you are starting with a new Intune tenant, you will not have any enrolled devices yet. 

    ![Screenshot of the device enrollment pane](media/tutorial-walkthough-intune-portal-02.png)
    
    Intune lets you manage your workforce’s devices and apps and how they access your company data. To use this mobile device management (MDM), the devices must first be enrolled in the Intune service. When a device is enrolled, it is issued an MDM certificate. This certificate is used to communicate with the Intune service. For more information about device enrollment, see [What is device enrollment?](device-enrollment.md)

3. From [Intune](https://aka.ms/intuneportal), select **Device compliance** to display details about compliance for devices managed by Intune.

    ![Screenshot of the device compliance pane](media/tutorial-walkthough-intune-portal-03.png)
    
    Compliance requirements are essentially rules, such as requiring a device PIN, or requiring device encryption. Device compliance policies define these rules and settings that a device must follow to be considered compliant. To use device compliance, you must have:
    - An Intune and an Azure Active Directory (AD) Premium subscription
    - Devices running a supported platform
    - Devices must be enrolled in Intune
    - Devices that are enrolled to either one user or no primary user.
    
    For more information, see [Get started with device compliance policies in Intune](device-compliance-get-started.md).

4. From [Intune](https://aka.ms/intuneportal), select **Device configuration** to display details about device profiles in Intune. 

    ![Screenshot of the device configuration pane](media/tutorial-walkthough-intune-portal-04.png)
    
    Microsoft Intune includes settings and features you can enable or disable on different devices within your organization. These settings and features are added to "configuration profiles". You can create profiles for different devices, different platforms, including iOS, Android, and Windows, and then use Intune to apply the profile to devices in your organization.   

5. From [Intune](https://aka.ms/intuneportal), select **Devices** to display details about your Intune tenant's enrolled devices. If you are starting with a new Intune enlistment, you will not have any enrolled devices yet. 

    ![Screenshot of the device enrollment pane](media/tutorial-walkthough-intune-portal-05.png)
    
    The device pane not only provides the number of enrolled devices, and also provides some basic details about your Intune tenant. Once you have enrolled devices, you can click **All deivces** to display a list of devices for your Intune tenant. 

6. From [Intune](https://aka.ms/intuneportal), select **Client apps** to display app installation status.

    ![Screenshot of the client apps pane](media/tutorial-walkthough-intune-portal-06.png)
    
    As an IT admin, you can use Microsoft Intune to manage the client apps that your company's workforce uses. This functionality is in addition to managing devices and protecting data. One of an admin's priorities is to ensure that end users have access to the apps they need to do their work. Additionally, you might want to assign and manage apps on devices that are not enrolled with Intune. Intune offers a range of capabilities to help you get the apps you need on the devices you want to run them on. 

7. From [Intune](https://aka.ms/intuneportal), select **Conditional access** to display details about access policies.

    ![Screenshot of the conditional access pane](media/tutorial-walkthough-intune-portal-07.png)

    Conditional access refers to ways you can control the devices and apps that are allowed to connect to your email and company resources. In this topic, learn about device-based and app-based conditional access, and find common scenarios for using conditional access with Intune.

8. From [Intune](https://aka.ms/intuneportal), select **Users** to display details about .

    ![Screenshot of the Users pane](media/tutorial-walkthough-intune-portal-08.png)



9. From [Intune](https://aka.ms/intuneportal), select **Groups** to display details about .

    ![Screenshot of the Groups pane](media/tutorial-walkthough-intune-portal-09.png)


10. From [Intune](https://aka.ms/intuneportal), select **Help and support** to display details about .

    ![Screenshot of the Help and support pane](media/tutorial-walkthough-intune-portal-10.png)


11. From [Intune](https://aka.ms/intuneportal), select **Tenant Status** to display details about .

    ![Screenshot of the Tenant Status pane](media/tutorial-walkthough-intune-portal-11.png)

12. From [Intune](https://aka.ms/intuneportal), select **Troubleshoot** to reach a shortcut on troubleshooting tips, requesting support, or checking the status of Intune. This information is specifc the Intune user you select.

    ![Screenshot of the Troubleshoot pane](media/tutorial-walkthough-intune-portal-12.png)


## Configure the Azure portal

Azure allows you to customize and configure the view of the portal.

### Change the sidebar

The __sidebar__ on the left side of the Azure portal shows you a list of all available Azure services. This comprehensive list can be changed from the default view so that you can keep a persistent view of the services that matter most to you. The information below uses Intune as the example of a service to add to the top of the list.

![A user searching for Microsoft Intune in the 'More services' list.](./media/azure-add-intune1.png)

1. Select **All services** from the sidebar on the left side of the page.
2. Search for **Intune** in the filter box.
3. Select the **star** to add Intune to the bottom of the list of your favorite services.
4. Hover over the Intune service. Select and drag Intune using the **three vertical dots** on the right side of the service name.

### Change the dashboard

Your default landing page is the **dashboard**. This page is where you customize your tiles to show information that is most relevant to you.

![An image of the generic new dashboard. It shows the sidebar with all of the services on the left, then the main dashboard in the center. The dashboard modification buttons are along the top, with tiles that offer access to all resources, quickstart tutorials, service health, and Azure marketplace.](./media/azure-default-dashboard.png)

To modify your current dashboard, select the **Edit dashboard** button. If you don't want to change your default dashboard, you can also create a **New dashboard**. Creating a new dashboard gives you an empty, private dashboard with the **Tile Gallery**, which lets you add or rearrange tiles. You can find tiles by their **General** category, **Type**, through **Search**, and through a **Resource group** or **Tag**.

You can also add tiles directly to your dashboard from any **ellipsis** button and selecting **Pin to dashboard**.

![A closeup of the Users and Groups > All groups location in Intune, which has the "Pin to dashboard" option visible at the far right side of a group.](./media/azure-pin-to-dashboard.png)

This capability will be more relevant after you've added more content, like groups and users, to Intune.

### View services

(describe viewing 'all services')

Whenever you open Intune or any other service in Azure, the service is displayed in a **pane**. Some of the first workloads you use in Intune, like **Users**, **Groups**, and **Client apps**, all appear in a full screen pane. When you select the workload, it opens that pane in the full page. Other panes slide out from the right side of the pane when they open, and collapse underneath the main pane that they came from.

## Next steps

You can find more information about...

> [!div class="nextstepaction"]
> [In-depth Autopilot enrollment article](enrollment-autopilot.md)


