---
# required metadata

title: Migrate conditional access policies from Intune classic portal to the new Azure portal.
titleSuffix: "Intune on Azure"
description: Migrate conditional access policies from Intune classic portal to the new Azure portal.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgree
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Reassign conditional access policies from Intune classic portal to the new Azure portal

Starting in the new Azure portal, conditional access offers support for multiple policies per application along with more customizability.

## Before you begin

If you’re ready to move to the new Azure portal, you can follow the steps below to reassign the conditional access policies previously created either in the Intune classic portal:

- Gather the conditional access policies previously created in the Intune classic portal so you know what settings you need to reassign later.

- Follow the steps in this topic to recreate these policies in the new Azure portal.

- Disable the conditional policies in the Intune classic console once you have verified that the new policies are working as expected in the new Azure portal.

	- **Before you disable** the conditional access policies in the Intune classic portal:

		- **Create an exempt group to use with the policies applied by the Intune classic portal, and use the same group to apply policies created in the new Azure portal.**
			- This prevents the policies targeted by the Intune classic portal to be applied. The policies created and targeted to the same user group in the new Azure portal overwrite the ones applied in the Intune classic portal.
<br></br>
		- **Create a new group to target the conditional access policies in the new Azure portal:** If you choose this approach, you need to do the following:
			- Remove the users from the security groups that have conditional access policies targeted to in the Intune classic portal.
			- Once you removed the users from the group, you can delete the security groups entirely.
<br></br>
- If you have your conditional access policy settings configured to use Exchange Active Sync (EAS) in the Intune classic portal, see [instructions in this topic](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) to **reassign EAS conditional access policy settings in the new Azure portal**.

### To verify your device-based conditional access policies in the Intune classic portal

1.  Go to [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.

2.  Choose **Policy** from the left menu.

3.  Choose **Conditional access**, then select the Microsoft cloud service (Exchange Online, SharePoint Online, etc.) you created a conditional access policy for.

4.  Take notes of your conditional access settings and use these notes as reference to create the same conditional access policies in the new Azure portal.

### Intune app-based conditional access in Intune App Protection blade

The **Intune App Protection** blade in the new Azure portal enables admins to set app-based conditional rules so that only apps that support the Intune app protection policies are allowed access to corporate resources. You can choose to overlap these app-based conditional access policies using device-based conditional access policies. Depending on whether you want to combine the device-based and app-based conditional policies (logical AND) or provide an option (logical OR). If your conditional access policy requirements are:

- Require compliant device **AND** use the approved app.
	- You should set your conditional access policy using the [Azure AD conditional access blade](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br />
- Require compliant device **OR** use the approved app.
	- You should set your conditional access policy using the [Intune classic portal](https://manage.microsoft.com) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> This topic provides screenshots comparing the user experience in both Intune classic portal and the new Azure portal.

## To re-assign Intune device-based conditional access policies

1. Go to [Conditional access in the new Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and sign in with your credentials.

2. Choose **New policy**.

3. Provide a name for the policy.

4. Choose **Users and groups** under the **Assignments** section to target the new conditional access policy.
	
	![User group UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-1.png)

	> [!IMPORTANT] 
	> If you have all users selected in the Intune classic portal, include All users. The same applies for groups, if you have groups selected, you need to choose **select individual users and groups** to include those groups. Additionally, if you’ve have chosen the **Exempt groups** option in the Intune classic portal, you need to exclude those select groups in the new Azure portal.

5. After you chose your group, click **Select**, then **Done**.

6. Choose **Cloud apps** under the **Assignments** section.

7. On the **Cloud apps** blade, choose **Select apps**.

8. Choose the app you want to apply the new conditional access policy to, click **Select**.

9. Click **Done**.

	![Cloud app UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-3.png)

	> [!TIP] 
	> If you have multiple apps with the same policy, you can consider consolidating them into a single policy in the new Azure portal.

10. Choose **Conditions** under the **Assignments** section.

11. On the **Conditions** blade, choose **Device platforms**, then choose the applicable device platforms.

12. Once you finished choosing the device platforms, click **Done** twice.

	![Device platform UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-4.png)

	> [!TIP] 
	> If you have chosen individual platforms in the Intune classic portal, choose the individual platforms in the new Azure portal.

	> [!NOTE] 
	> You can specify the domain join or compliant options for Windows later.

13. Choose **Conditions** under the **Assignments** section.

14. On the **Conditions** blade, choose **Client apps**, then choose the applicable client app.

15. Once you finished choosing the client app, click **Done** twice.

	![Client apps UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-6.png)

16. If you have chosen the browser settings in the Intune classic portal, select both **Browser** and **Mobile apps and desktop clients** in the new Azure portal. In case you have not chosen the browser settings in the Intune classic portal choose **Mobile apps and desktop clients** only. 

17. Choose **Grant** under the **Access controls** section.

18. Choose **Require device to be marked as compliant** under **Grant Access Controls,** then click **Select**.

	![Grant access UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-8.png)

19. If you have a policy to require domain joined Windows devices, and you also allow Intune-enrolled and compliant Windows devices, choose **Require domain joined device** and **Require device to be marked as compliant** along with **Require one of the selected controls**.

20. If you do not allow Intune enrolled and compliant Windows devices, exempt the Windows policy from the current policy and then create a separate policy with **Device platform**s set to **Windows ,** include the other conditions as set per above, and choose **Require domain joined device** under **Grant Access Controls**.

21. Turn on the **Enable policy** toggle on the **New** conditional access policy blade, then click **Create**.

	![Enable ca policy UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-11.png)

## To reassign Intune device-based conditional access policies for EAS clients

If you have configured Exchange Active Sync (EAS) settings as part of an Exchange Online policy in the Intune classic portal, you need to create a second conditional access policy in the new Azure portal.

1. Go to [Conditional access in the new Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and sign in with your credentials.

2. Choose **New policy**.

3. Provide a name for the policy.

4. Choose **Users and groups** under the **Assignments** section to target the new conditional access policy.

	![User group UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-12.png)

	> [!IMPORTANT] 
	> If you have all users selected in the Intune classic portal, include All users. The same applies for groups, If you have groups selected, you need to choose **select individual users and groups** to include those groups. Additionally, if you’ve have chosen the **Exempt groups** option in the Intune classic portal, you need to exclude those select groups in the new Azure portal.

5. After you chose your group, click **Select**, then **Done**.

6. Choose **Cloud apps** under the **Assignments** section.

7. On the **Cloud apps** blade, click **Selected apps**, choose **Exchange Online**, click **Select**, then click **Done**.

	![Cloud apps UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-14.png)

	> [!IMPORTANT] 
	> Conditional Access policies for EAS clients cannot include any other cloud app.

8. On the **Conditions** blade, choose **Client apps**, then choose the applicable client app. If you have chosen to block clients that aren’t supported by Intune, use the **Apply policy only to supported platforms** option.

	![Client apps UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-15.png)

9. Once you finished choosing the client app, click **Done** twice.

10. Choose **Grant** under the **Access controls** section.

11. Choose **Require device to be marked as compliant** under **Grant Access Controls,** then click **Select**.

	![Grant access UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-16.png)

12. Turn on the **Enable policy** toggle on the **New** conditional access policy blade, then click **Create**.

	![Enable ca policy UI comparison between Intune classic and the New Azure portal](./media/reassign-ca-17.png)

## Disable conditional access policies in the Intune classic portal
### Before you start

Once you reassigned your conditional access policies in the new Azure portal, it's important to gradually disable the conditional access policies previously created in the Intune classic portal. Additionally, you might need to use the same security group to apply the conditional access policies created in the new Azure portal

- See the [before you begin](#before-you-begin) section at the beginning of this topic before disabling your conditional access policies in the Intune classic portal.

### To disable the conditional access policies

1.  Go to [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.

2.  Choose **Policy** from the left menu.

3.  Choose **Conditional access**, then select the Microsoft cloud service (Exchange Online, SharePoint Online, etc.) that you created a conditional access policy for.

4.  Uncheck the option **Enable conditional access policy**, then click **Save**.

	![Disable conditional access policies Intune classic portal](./media/reassign-ca-18.png)

## See also

- [Common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md)
- [App-based conditional access with Intune](app-based-conditional-access-intune.md)
- [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)