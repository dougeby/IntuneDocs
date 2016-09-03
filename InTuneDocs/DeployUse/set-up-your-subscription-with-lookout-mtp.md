---
# required metadata

title: Setup your subscription with Lookout MTP | Microsoft Intune
description: This topics provides details on how to configure Lookout MTP.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Set up your subscription for  Lookout mobile threat protection
To get your MTP tenant ready for the service, Lookout Support will need the following information about your Azure Active Directory (Azure AD). 

* AAD Tenant ID
* AAD Group Object ID for full Lookout MTP console access
* AAD Group Object ID for restricted Lookout MTP console access (optional)  

## Before setting up mobile threat protection for you subscription
Log into the AAD management portal https://manage.windowsazure.com and select your subscription. 

![screenshot of the Azure AD page showing the name of the tenant](../media/mtp/aad_tenant_name.png)
When you choose the name of your subscription, the resulting URL  includes the subscription ID.  If you have any issues finding your subscription ID, the [Microsoft support article](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) provides additional tips.   
## Getting your Azure Active Directory ID
The Lookout MTP console supports 2 levels of access:  
* **Full Access:** AAD admin can create a group for users that will have Full Access and optionally they may create a group for users that will have Restricted Access.  Only users in these groups will be able to login to the **Lookout MTP Console**.
* **Restricted Access:** No access to several configuration and enrollment related pages; read-only access to the **Security Policy** page.  

For more details on the permissions, read [this article](https://personal.support.lookout.com/hc/en-us/articles/114094105653) on the Lookout website.

The **Group Object ID** can be found on the properties page of the group in the AAD management console.
![screenshot of the properties page with GroupID field highlighted](../media/mtp/aad_group_object_id.png)

Lookout Support will engage the primary contact specified in a phone conversation to provide overview information and will onboard your subscription and create your Lookout MTP Enterprise account, using the information that you collected as described above.


## Configure your subscription with Lookout MTP
### Step 1: Setup your MTP
After Lookout Support creates your Lookout MTP Enterprise account, you may login to the Lookout MTP Console.   An email from Lookout is sent to the primary contact for your company that you specified during setup with a link to the login url   https://aad.lookout.com/les?action=consent

You must use a user account with the AAD role of Global Admin when you first log in to the Lookout MTP console, since the Lookout MTP requires this to register your Azure AD tenant.   Subsequent logins will not require the user to have this level of AAD privilege.  In this first login, a consent page will be displayed. Choose **accept** to complete the registration.

![screenshot of the first time login page of the Lookout MTP console](../media\mtp/lookout_mtp_initial_login.png)
Once you have accepted and consented, you are redirected to the Lookout MTP Console. Subsequent logins after the initial registration, can be done using the URL:  https://aad.lookout.com

See the [troubleshooting article](troubleshooting-lookout-integration)  for diagnosing any login issues.

The next steps outline the tasks that must be done to complete the Lookout MTP set up within the Lookout MTP Console.

### Step 2: Configure the Intune connector
### Step 3: Configure enrollment groups
### Step 4: Configure state sync
### Step 5: Configure email notifications
### Step 6: Configure threat classification
## Watching enrollment
## Next steps
