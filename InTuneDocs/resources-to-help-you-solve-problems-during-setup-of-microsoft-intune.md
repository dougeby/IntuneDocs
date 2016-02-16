---
title: Resources to help you solve problems during setup of Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6865f1fb-c2c1-47af-83f5-5704e7210a49
author: Nbigman
robots: noindex,nofollow
---
# Resources to help you solve problems during setup of Microsoft Intune
Because [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] is a cloud service, there should be little need to repair or troubleshoot operational issues. When you experience problems in accessing the service, the following sections can help you identify next steps to take.

## <a name="BKMK_ResolveSetupProblems"></a>Tips to solving problems with setup and configuration of Microsoft Intune
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not generate setup or operation logs that you can use to troubleshoot problems.

Your administrative actions use a web browser to connect to the cloud service. Problems in accessing the service are typically due to one of the following:

|Problem|Details|
|-----------|-----------|
|Insufficient permissions to the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)]|To use the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)] to manage more than your own user profile, your account must:<br /><br />-   have a license to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]<br />-   have a sign-in status of **Allowed** to sign in<br />-   be a [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)] tenant administrator<br /><br />For information, see [Intune administrator accounts and special permissions](../Topic/What-to-know-before-setting-up-Microsoft-Intune.md#BKMK_AdminAccounts).|
|Network access including:<br /><br />-   Domains used by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]<br />-   Traffic on the network<br />-   Web browser support|To connect to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you must:<br /><br />-   use a supported web browser<br />-   have access on your network through firewalls and proxy servers to the various domains that are in use by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.<br /><br />For information about requirements and configurations necessary to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see:<br /><br />-   [Infrastructure requirements](../Topic/Network-infrastructure-requirements-for-Microsoft-Intune.md#BKMK_InfrastructureReqs)<br />-   [Web browsers supported by Microsoft Intune](../Topic/Network-infrastructure-requirements-for-Microsoft-Intune.md#BKMK_SupportedBrowsers)|
|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service availability|To view details online, or subscribe to RSS feeds about the health of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service, see:<br /><br />-   [Microsoft Intune service](http://status.manage.microsoft.com/)|

## See Also
[Introduction to Microsoft Intune](../Topic/Introduction-to-Microsoft-Intune.md)

