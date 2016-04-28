---
title: Help for Microsoft Intune Partners
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9cb7da1d-8ecb-4b08-818a-54782e846def
author: Brenduns
---
# Help for Microsoft Intune Partners
The partner portal and its services are an extension of your [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] subscription that is associated with your partner identity. When you sign in to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] account portal with a work account that is associated with your partner ID, you have access to the partner portal by using the **Partner** link at the top of the account portal.

|What do you want to do?|Details|
|---------------------------|-----------|
|**Verify your company information**|Always ensure that your company information, like phone numbers and email addresses, is correct as this is visible to your customers.<br /><br />To verify your information, in the left-hand pane of the partner portal, click your company name to view and edit your company information.<br /><br />Your user account must be a [global administrator](http://technet.microsoft.com/library/dn646966.aspx#BKMK_AdminAccounts) to edit your company information.|
|**Find customers**|Use the partner portal to [Find and help customers](../Topic/Help-for-Microsoft-Intune-Partners.md#BKMK_FindCustomers) you might want to offer services to, or that you are already working with.<br /><br />You can search for customers who subscribe to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] by their user account name, or by their domain name.|
|**Create and send trial invitations and purchase offers**|As a partner, you can [Create trial invitations and purchase offers](../Topic/Help-for-Microsoft-Intune-Partners.md#BKMK_CreateTrials) that make it easy for your customers to first try the service, and to make a purchase.<br /><br />Offers you create contain a link where customers can access the offer. The link contains an embedded code that identifies you as the subscription advisor.|
|**Offer delegated administration**|As a partner, you can [Offer delegated administration](../Topic/Help-for-Microsoft-Intune-Partners.md#BKMK_OfferAdmin), which allows users from your company to provide additional support to your customers.|
|**Configure your users to be delegated administrators**|In addition to managing your own company subscription, (including giving your users administrative access to your subscription), you can [Give users permission to act as delegated administrators](../Topic/Help-for-Microsoft-Intune-Partners.md#BKMK_AssignDelAdmin) for companies you support.|
|**Administer a customer**|When your users have administrative access to companies you support, they can use the partner portal to [Administer a customer as a delegated administrator](../Topic/Help-for-Microsoft-Intune-Partners.md#BKMK_Administer).|
You continue to use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] account portal and administration console to manage your own subscription, including devices and users. For information about managing [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see the [Documentation for Microsoft Intune](../Topic/Documentation-for-Microsoft-Intune.md).

## <a name="BKMK_FindCustomers"></a>Find and help customers
Use the partner portal to identify customers that you can help. After you locate a customer, you can provide services or assistance, which include:

-   Offer trial and paid subscriptions

-   Administer customers who have accepted delegated administration

-   Create and submit service requests

-   Reset user passwords

To find a customer in the partner portal, search for a customer’s user name or domain name. If you are already a delegated administrator for a customer, you can search for any domain name that is associated with that subscription.

#### To find and help a customer

1.  On the **Partner Overview** page of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] partner portal, click **Lookup user or domain**.

2.  On the **Search for user or domain** page, enter the complete user name (someone@contoso.com) or the domain name (contoso.com) you want to find. The name must be an exact match. Wild cards are not supported. Click **Next** to begin the search.

3.  When a match is found, a results page appears with information about the customer account, and action links at the top of the page. Click the link for the action you want.

    |Action|Details|
    |----------|-----------|
    |**Administer on behalf of**|Only available when the customer has given you permissions as a delegated administrator.<br /><br />This link opens a [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] account portal to the customer’s subscription.<br /><br />-   Confirm the subscription you are managing by viewing the company name on display at the top of the left hand pane.<br />-   When your partner credentials are configured for **Limited administration**, you will not have access to the **Manage**, **Purchase**, or **Domain** nodes of your customer’s subscription.<br />-   If you click a link to an available console, like the company portal or admin console, you are directed to that console for your company, and not the console for the customer.|
    |**Create service request**|Opens a service request on behalf of your customer.|
    |**Show all administrators**|Displays a list of all tenant administrators for your customer’s company.|
    |**Reset password**|Resets the password for your customer’s user account in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].<br /><br />-   When you are a global administrator, you can reset passwords from the partner portal.<br />-   If you are a limited administrator, you can only reset passwords from the customers account portal.|

## <a name="BKMK_CreateTrials"></a>Create trial invitations and purchase offers
A trial invitation can contain an offer for only one trial subscription at a time.

Purchase offers can contain one or more subscriptions, which allows you to bundle multiple subscriptions into a single offer.

**Trials and offers have the following in common:**

-   When you create a trial invitation or an offer, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] creates a message that contains the details. You can then customize this message and send it to your customer.

-   After you customize the message, you can click **Open in email** to automatically create an email message with the message details. You can also manually copy and paste the message into a different communication format.

-   The message details contain an link with an embedded code that identifies your company as the subscription advisor associated with the services that you specify.

-   You can use the same message for multiple customers. There is nothing in the trial invitation or purchase offer that is tied to a specific customer.

-   When a customer clicks on the link in the message details, they are presented with the trial or purchase offer, with the details you specified.

-   A customer can accept the trial or purchase offer without accepting an offer of delegated administration.

When a customer accepts an offer from the link in the message, they are directed to a standard sign up page and process for the trial or purchase of the service. The sign up page link contains the embedded code that identifies your company as the subscription advisor.

**When customizing your message, consider the following:**

-   Identify yourself as an authorized Microsoft partner.

-   Let customers know that they will be billed directly by Microsoft.

-   Tell customers how they can contact you with questions about the service or the offer.

-   Your customers control the number of user licenses purchased. They can change the number of licenses when they accept the offer.

-   If you offer delegated administration, explain what it means, and what your responsibilities are.

#### To create and send a trial invitation or purchase offer

1.  On the **Partner Overview** page of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] partner portal, click **Send trial invitations** or **Create purchase offers**.

2.  In the wizard, configure the available options:

    -   **Partner office**: If your company has multiple offices, select the office that you want to associate with this trial invitation. If your office is not listed, add new locations at the [Microsoft Partner Network](http://go.microsoft.com/fwlink/?linkid=235720) website. It can take up to 24 hours before new entries appear in the **Partner office** list.

    -   **Usage location**: Select the location where your customer will use the services.

    -   **Trial subscriptions** (for trials), or **Subscriptions** (for purchase offers): The list of subscriptions that are available is determined by the usage location of your customer’s country or region.

        For purchase offers, you are prompted to enter the number of user licenses after you select a subscription.

    -   **Delegated administration**: Select this option if you want to offer your customer delegated administration. Customers can accept a trial invitation or offer with or without accepting delegated administration.

3.  When you are finished click **Open in email** to open a new email that contains the link to the invitation, or manually copy and paste the link to a message format of your choice and then send this to your customer.

    -   When you click **Open in email**, if User Account Control (UAC) is enabled on your computer, a blank webpage might open in addition to the email message.

    -   Make a note of the **Quote ID**. You can use this ID to track the offer on the Microsoft Online Services Partner Commerce Dashboard.

## <a name="BKMK_OfferAdmin"></a>Offer delegated administration
As an authorized Microsoft partner, you can offer delegated administration. This means you can offer to administer a company’s subscription on their behalf.

Delegated administrators:

-   **Are tenant administrators** that can use the account portal to perform simple tasks like adding users and resetting passwords for the customer, or more technical tasks like adding a domain to the customer’s account.

-   **Are not service administrators** and therefore do not have access to manage the day-to-day operations for the customer, like software deployment, as configured in the administration console.

Before you can administer a customer's subscription, the [Manage partner relationships](../Topic/Maintain-Microsoft-Intune.md#BKMK_ManagePartners). To obtain customer approval, you can send an offer for delegated administration, which the customer can accept. A customer can accept the trial subscription or purchase offer without accepting your offer of delegated administration.

-   You can offer of delegated administration when you create trial invitations and purchase offers. This can help build a strong relationship with your customer from the beginning.

-   You can offer delegated administration to a customer that has previously purchased a subscription.

After a customer accepts your offer and configures your partner ID as a delegated administrator, users from your company that have permissions to access the customer’s company, can serve as a delegated administrator.

#### To offer delegated administration to an existing account

1.  On the **Partner Overview** page of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] partner portal, click **Send delegated administration offers**.

2.  Click **Open in email**, or copy the link for the offer and paste it manually into an email message.

3.  When your customer receives your offer that contains the link, they can follow it to authorize you as a delegated administrator.

You can also include an offer of delegated administration when you create a trail subscription or purchase offer by selecting **Include authorization for delegated** when selecting options for the trial or offer.

## <a name="BKMK_AssignDelAdmin"></a>Give users permission to act as delegated administrators
In the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] account portal of your subscription, you can configure your users to have administrative access to companies that you support:

-   You can make this partner-only configuration when you create new user accounts, or when you edit existing user accounts.

-   Users do not need to be an administrator of your company to be given administrative access to companies you support.

Users that are delegated administrators can:

-   Access your partner portal

-   Search for users and domains of customers

-   Create trial invitations and purchase offers, and offer delegated administration to customers

-   Manage customer subscriptions based on the role assigned to their user account

For information about configuring administrative users, see [Task 5: Assign administrative users](../Topic/Get-started-with-a-paid-subscription-to-Microsoft-Intune.md#BKMK_AssignAdmins). For information about administrator roles and permissions, see [Assigning administrator roles](http://technet.microsoft.com/library/hh967622).

#### To configure an user to be a delegated administrator

1.  In the [Microsoft Intune account portal](https://account.manage.microsoft.com/) for your company, click **Users**.

2.  Select the user account that you want to configure, and then click **Edit**.

3.  On the Settings tab, under **Assign administrative access to companies you support**, click **Yes** and then select the appropriate role for this account:

    -   **Full administration**: Gives the user privileges equivalent to the global administrator role for the companies you support.

    -   **Limited administration**: Gives the user privileges equivalent to the password administrator role for the companies you support.

4.  Click **Save** to complete the procedure.

Permissions as a delegated administrator apply only for administering a customer’s subscription. They do not give the user tenant administrator or service administrator permissions to your company subscription.

## <a name="BKMK_Administer"></a>Administer a customer as a delegated administrator
After a customer configures your partner ID as a delegated administrator, your users that are configured as delegated administrators can administer the customer’s subscription.

**When you manage a customer’s subscription:**

-   You can only access the customer’s account portal

-   When you navigate away from the customer’s account portal, the administration session for that customer ends

-   If you use the back button in the browser to try to return to the customer’s portal, you are instead returned to the account portal for your own subscription

-   To return to the account portal for the customer, you must sign in to your partner portal, search for, and then administer the selected customer

#### To administer a customer

1.  Sign in to your company’s partner portal.

2.  On the **Partner Overview page**, click **Lookup user or domain**, and then search for the customer subscription you want to administer.

3.  After the customer is found, click **Administer on behalf of**.

When the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] account portal opens, confirm you are working with the customer account by viewing the company name in the upper left corner of the left pane, and then perform the required administration tasks.

