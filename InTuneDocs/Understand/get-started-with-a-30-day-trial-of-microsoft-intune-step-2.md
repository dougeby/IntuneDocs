---
# required metadata

title: Add users to your 30-day evaluation of Intune | Microsoft Intune
description: How to add users, individually or in bulk, when you sign up for a free, 30-day evaluation of Intune
keywords:
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Add users to your 30-day evaluation of Microsoft Intune
Now that you have set up your account, you'll use either the **New Users** wizard to add individual user accounts to Intune, or the **Bulk add users** wizard to add users in bulk (see the instructions in this section).  Before you get started, it's important that you understand how Intune handles administrator accounts.

A tenant administrator  uses the Office 365 admin center to add  users to the Microsoft Intune **Users Group**. Adding users to the  **Users Group** assigns Intune subscription licenses to users and is also how you make those users to show up in the Microsoft Intune administration console.

Administrator accounts for Intune aren't created in the Office 365 admin center,  as regular user accounts are. Instead, you  assign  either read-only access or full access administrative rights to users by using the administration console in the **Administration** workspace under **Administration Management**. Service administrators that are assigned read-only access cannot change Intune settings, but they can view data and run reports. Service administrators with full access have all available administrative rights.

You can view tenant administrator information by using the Intune administration console, but you cannot create tenant administrators there. By default, the subscription owner becomes a tenant administrator for your Microsoft Intune service and has full access to both the Office 365 admin center and the Intune administration console. We recommend that you create a least one extra tenant administrator account by using the Office 365 admin center to help delegate tasks and to ensure that you don’t get locked out of your Intune service administrator account if you forget your password.

## Add individual user accounts
Use the following steps to create additional user accounts in your evaluation tenant. Remember, each user account that you add counts as one of the 100 licenses that  you get as part of your Intune free evaluation.

1.  In the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkID=787455), choose **Add Users** &gt; **New**&gt; **User** to start the **New users** wizard.

2.  On the **Details** page, complete the required fields.

3.  On the **Settings** page, set the **location** for the user.

4.  On the **Group** page, choose **Next** to accept the default and assign a license for Intune to the user’s account.

5.  On the **Email** page, specify up to five email addresses that will receive notification of the user name and temporary password for the account. Separate multiple email addresses by semicolons (;). When you're done, chose **Create** to add the user to your subscription.

6.  On the **Results** page, you can view the new account name and its temporary password. Intune automatically creates the temporary password.

7.  When the new user  appears in the Office 365 admin center, verify that the new user was created successfully:

    1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** &gt; **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under  **Intune Company Portal**.

    2.  Open a new browser window in “privacy mode” (in Internet Explorer, choose **Tools** &gt; **InPrivate Browsing**), or open a new browser window on a different device, and then navigate to the URL that you copied in the previous step. When users sign in for the first time, they must provide a new password for the account.

## Add users in bulk
To add users in bulk to Intune,  use the **Bulk add users** wizard to upload a comma-separated values (CSV) file that contains your user data. Links in the wizard enable you to download a blank template and sample CSV file. The first row of your CSV file must contain, in the correct order, each of the user data column labels. Then, for each user in the CSV file, you must include the **user name** (like **bob@contoso.com**) and a **display name** (like **Bob Kelly**).

1.  In the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkID=787455), choose **Users** &gt; **New**.

2.  Choose **Bulk add** to start the Bulk add users wizard.

3.  On the **Select file** page, choose **Browse** to specify and load an existing CSV file from your computer. You can also download a sample CSV file or blank template file by using the links in the wizard.

4.  On the **Verification** page, review the results, and then choose **View** for more details.

5.  On the **Settings** page, confirm that the sign-in status is **Allowed**, and set the **location**. These settings apply to all user accounts added by the CSV file.

6.  On the **Group** page, choose **Next** to accept the default and assign a license for Intune to all user accounts added by the CSV file. By default, the check box is selected, which assigns a license for Intune to each account.

7.  On the **Email** page, specify up to five email addresses to receive notification of the user names and temporary passwords that Intune creates for each account. Separate multiple email addresses with semicolons (;). Choose **Create** to add the users to your subscription.

8.  On the **Results** page, you can view the account names and temporary password for each user account.

Each user account that you added by importing it now appears in the **Users** node of the Office 365 admin center. When new users sign in for the first time, they must specify a new password for their user account.

### Next steps
Congratulations! You have just completed step 2 of the *Microsoft Intune evaluation* walkthrough.

>[!div class="step-by-step"]

>[&larr; **Sign up for an evaluation**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Create groups** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  
