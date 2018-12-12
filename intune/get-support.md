---
# required metadata


title: How to get support for Microsoft Intune
titlesuffix: Microsoft Intune
description: Get online and telephone support for Microsoft Intune paid and trial subscriptions.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# How to get support for Microsoft Intune

[!INCLUDE [azure_portal](./includes/note-for-both-portals.md)]

Microsoft provides global technical, pre-sales, billing, and subscription support for Microsoft Intune. Support is available both online and by phone for paid and trial subscriptions. Online technical support is available in English and Japanese. Phone support and online billing support are available in additional languages.

>[!IMPORTANT]  
> For technical support with third-party products that work with Intune (like Saaswedo, Cisco, or Lookout), contact the supplier of that product first. Before you open a request with Intune support, make sure you configured the other product correctly.
>
> For information about troubleshooting issues related to Microsoft Intune, see the [Troubleshoot section](help-desk-operators.md) of the Intune documentation.

As an IT admin, you can use the **Help and Support** option to file an on-line support ticket for Intune from the Azure portal. To create a support ticket, your account must be assigned one of the following [administrator roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal):

- Intune administrator
- Global administrator
- Service administrator  


## Help and Support experience
> [!TIP]   
> In January of 2019, a new Help and Support experience is rolling out to all tenants. If your tenant does not yet have this new experience, you can find information about the previous experience in [Deprecated Help and Support experinece](#deprecated-help-and-support-experience), in this article.  

The Help and Support experience for Intune is available from the [Microsoft 365 Device Management portal](http://devicemanagement.microsoft.com) and from all of the blades (or pages) under Intune in the Azure portal. 

![Intune blades](./media/get-support/intune-blades.png)


This new experience is similar to the experience seen in the [Microsoft 365 admin center](https://portal.office.com/AdminPortal/Home), and replaces the [previous Help and Support experience](#deprecated-help-and-support-experience). 

To access Help and Support, use the following:  
- **Device Management Dashboard:**
   - Select any available option for **Help and Support**
   - Select the **?** icon in the upper-right corner of the portal

- **In the Azure Portal:**
   - Select **Help and Support** from any Intune blade or page

   Selecting either the **?** icon from the upper-right corner, or **Help + Support** from the left-side navigation pane from any location in the Azure portal opens *Help + Support* for Azure, which isn't tailored to Intune.   

WIth the new experience, you gain access to the **Need help?** view, as seen in the following image from the Device Management dashboard:  
![Device Management dashboard and the Need Help? page](./media/get-support/help-support-dashboard.png)

In this view you can do the following actions:

1. [Specify details](#specify-details-about-an-issue) about the specific problem you want help with  
2. [View context-sensitive help](#view-context-sensitive-help) and related solutions that are based on the details you specified  
3. [Get support](#get-support), using either email or the phone  
4. [View support cases](#view-support-cases) you have previously opened using this new workflow  

### Specify details about an issue
When you open Help and Support from a location that is supported by the new experience, the **Need help?**  page opens. On this page, you can specify details about an issue. As you enter details, the console offers common queries based on the keywords you use. You can select an offered choice or complete your own issue description. If you enter your own description, select **Get help** to submit it. After you submit a query, the console returns context-sensitive information that can help to solve the issue.

The following are examples of queries you might submit:
  
- *Can’t restore iOS device*  
- *Can’t create conditional access policy*  

![Specify the issue on the Need Help? page](./media/get-support/describe-the-issue.png)

### View context-sensitive help
After you select an offered choice or submit your own query, context-sensitive results appear under **View solutions**. These results include both Intune specific self-help guidance and additional results returned from a web-search based on the query criteria.  
![View-results](./media/get-support/view-results.png)

### Get support
If the self-help or web-based guidance doesn’t help you resolve the issue, you can use the console to open an email or phone support issue.  
On the **Need help?** page, select the option you want to use.  

- For an email request, provide your email address and optionally, you can add attachments to your submission. Select **Send** to open the request.  

  ![Email request](./media/get-support/email-support.png)
  
- For a phone request, provide your phone number. Optionally, you can include your email address and add attachments to your submission. Select Call me to submit the request.  

   ![Phone request](./media/get-support/phone-support.png)

### View support cases
Select the history button to view the support incidents that you've created.  

![View support cases](./media/get-support/view-support-tickets.png)

- Only the support cases that you open by using the new workflow are visible from within this workflow. To view them, use a Help and Support view from the Device Management console or from an Intune blade in the Azure portal. These cases have numbers that are eight digits long. You can also view these cases from the Microsoft 365 admin center.  

- Cases that you opened when not using the Intune Help and Support experience are unchanged. To view them, you must use a help and support view that isn't part of the Intune experience, or Device Management dashboard. These cases have numbers that start with **117** or **118** and are 15 digits long. To view them:

    1. Sign in to  Azure (<https://portal.azure.com>) with your Intune admin credentials, select the *?* icon in the upper-right corner of the portal, and then select *Help + support* to go to the [Azure Help + support](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) page.

    2. On the **Help + support** page you can view the list of **Recent support requests**, and select them to view additional details.


## Deprecated Help and Support experience
The following information describes the Help and Support experience for Intune that is deprecated beginning in January of 2019. Use this information until your tenant has the new support experience available. 

### Get context-sensitive help
After you sign in to the Azure portal and open Intune, you can select **Help and support** from any Intune blade in the Azure portal to view solutions to common problems for that area of Intune.

If the common solutions don't help, you can select **support request** to create a new support request that opens to the **Basics** tab of the Azure *Help + support* page. To continue and create a support ticket, go to *step 3* in the following procedure, [Create an online support ticket](#create-an-online-support-ticket).

### Create an online support ticket

1. Sign in to the Azure portal (<https://portal.azure.com>) with your Intune admin credentials, select the **?** icon in the upper-right corner of the portal, and then select **Help + support** to go to the [Azure Help + support](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) page.

   ![Screenshot of Azure portal help and support question mark link with the Help + support link highlighted](./media/azure-get-support.png)

2. On the Azure **Help + support** page, select **New support request**.

   ![Screenshot of Azure portal help and support page with New support request link highlighted](media/azure-support-ticket-link.png)

3. On the **Basics** tab, for most Intune technical support issues, choose the following options:
   - **Issue type**: **Technical**
   - **Subscription**: <*your subscription*>
   - **Service**: **Microsoft Intune**
   - **Problem type**: Choose your problem type from the drop-down menu.
   - **Problem subtype**: Choose the problem subtype from the drop-down menu.
   - **Subject**: Briefly describe the issue that you are having.

   ![Screenshot of the basics tab on the Help + support - New support request page](./media/get-support/help-new-support-case-basics.png)

   Choose **Next: Solutions** to continue.
4. On the **Solutions** tab, review the recommended steps that might help you solve your problem without filing a ticket. If you still want to create a support request after looking through the steps, click **Next: Details**.

   ![Screenshot of the solutions tab on the Help + support - New support request page](./media/get-support/help-new-support-case-solutions.png)
5. On the **Details** tab, fill out the details for your problem, the support method, your contact information, and then click **Next: Review + create**.

   ![Screenshot of the details tab on the Help + support - New support request page](./media/get-support/help-new-support-case-details.png)
6. Review the information, verify that it's correct, and then choose **Create** to submit your support request.

   ![Screenshot of the review + create tab on the Help + support - New support request page](./media/get-support/help-new-support-case-create.png)

<!--
  - **Support plan**: **Technical support - included** (for Intune technical issues, support is complimentary) or **Premier**
     >[!IMPORTANT]
     >- If you are a **Premier customer** and don't see **Support plan: Premier**, contact your Technical Account Manager for help linking your contract and tenant.
     >- Support for Intune, and for Intune when used with Configuration Manager, is free of charge. To review details of the Premier Support offering, see the [Description of Services](https://enterprise.microsoft.com/en-us/services/services-list/) documentation, section 5.3.3 "Advisory Services."

4. On the **Problem** blade, to make sure your request is addressed by the right subject matter expert for your problem, select the following options:

   - **Severity**
   - **Problem type**
   - **Category**

     These details also let us provide **Related help** that might solve your problem without filing a ticket.

     ![Screenshot of Azure portal help and support page with Problem items filled out and displaying solutions based on your problem](./media/support-need-solutions.png)

     To help the support team research and resolve your problem, enter the following information:
    
   - **Details**
   - **Date**
   - **Time**
   - **Supplemental data**

   Choose **Next**.

5. Provide **Contact information** for this support request. Microsoft support uses this information to contact you.
6. Choose **Create** to submit your support request.
-->
>[!IMPORTANT]
>If you have a billing or subscription question, you can open a case to get support through the [Office Admin Center](https://portal.office.com/Support/SupportEntry.aspx).

### View support requests
You can view a support request from within the Azure portal. To do so:

1. Sign in to  Azure (<https://portal.azure.com>) with your Intune admin credentials, select the **?** icon in the upper-right corner of the portal, and then select **Help + support** to go to the [Azure Help + support](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) page.

2. On the **Help + support** page you can view the list of **Recent support requests**, and select them to view additional details.



## Additional resources
- [Contact assisted phone support for Microsoft Intune](phone-support-contact.md)
- [Billing and subscription management support](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Volume licensing](http://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Troubleshoot Intune issues](help-desk-operators.md)