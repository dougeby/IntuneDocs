---
title: Reference for the Microsoft Intune administrative consoles
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 345b5264-ab29-4c46-b122-e986fa320c9b
author: Staciebarker
robots: noindex,nofollow
---
# Reference for the Microsoft Intune administrative consoles
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Different <link xlink:href="5d1ac59c-a885-4276-8576-f3cf81c2d268#BKMK_AdministrativeTasks">administrative tasks</link> for <token>wit_firstref</token> require you to use one of two administrative websites, the <token>wit_icp_1</token> or the <token>wit_adminconsole</token>.</para>
    <para>The following information can help you identify where in each console you do various tasks.</para>
  </introduction>
  <section address="BKMK_AccountPortal">
    <title>Microsoft Intune Account Portal</title>
    <content>
      <para>The <externalLink><linkText>Microsoft Intune account portal</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkID=232813</linkUri></externalLink> is where tenant administrators manage the subscription.</para>
      <para>A tenant administrator’s assigned administrator role determines what details that user can view and manage in the account portal. For example, an administrator with the Billing Administrator role can manage all options under <ui>Subscriptions</ui>, has read-only access to <ui>Users</ui> and <ui>Security Groups</ui>, but cannot view the <ui>Domains</ui> page of the portal.</para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <thead>
          <tr>
            <TD>
              <para>Node</para>
            </TD>
            <TD>
              <para>Page</para>
            </TD>
            <TD>
              <para>Tasks</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>Dashboard</para>
            </TD>
            <TD>
              <para>Not applicable</para>
            </TD>
            <TD>
              <para>View information about common tasks you do to set up your subscription.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Setup</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>There are no configurations to make on this page. However, the information you find here can help you to set up key components of your subscription.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="3">
              <para>Management</para>
            </TD>
            <TD>
              <para>Users</para>
            </TD>
            <TD>
              <para>Manage user accounts, including: </para>
              <list class="bullet">
                <listItem>
                  <para>Add, edit, delete users, and reset passwords.</para>
                </listItem>
                <listItem>
                  <para>Assign users a license to use <token>wit_nextref</token>.</para>
                </listItem>
                <?xm-deletion_mark author="" time="20150716T115532-0500" data="&lt;maml:listItem xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
                  &lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;Assign administrator roles (permissions) to users to grant access to the account portal.&lt;/maml:para&gt;
                &lt;/maml:listItem&gt;"?>
              </list>
              <para>This page also contains links to:</para>
              <list class="bullet">
                <listItem>
                  <para>Set up single sign-on for your users.</para>
                </listItem>
                <listItem>
                  <para>Set up Active Directory synchronization.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Security Groups</para>
            </TD>
            <TD>
              <para>Manage logical groups of user accounts that are stored in your instance of Azure AD. You can use security groups as criteria for groups you create in the <ui>Groups</ui> page of the <token>wit_adminconsole</token>.</para>
              <para>This page also contains links to:</para>
              <list class="bullet">
                <listItem>
                  <para>Set up single sign-on for your user.</para>
                </listItem>
                <listItem>
                  <para>Set up Active Directory synchronization.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Domains</para>
            </TD>
            <TD>
              <para>Set up the domain name for your subscription.</para>
              <para>By default, your subscription includes a domain name as part of the Microsoft Online Services domain, and appears as <userInput>&lt;domain&gt;.onmicrosoft.com</userInput>.</para>
              <para>After you subscribe to <token>wit_nextref</token>, you can reconfigure you subscription to use a domain name you own.</para>
              <para>For more information, see <externalLink><linkText>Internet domain management</linkText><linkUri>http://technet.microsoft.com/library/hh969248.aspx</linkUri></externalLink>, in the Microsoft Azure AD documentation.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="4">
              <para>Subscriptions</para>
            </TD>
            <TD>
              <para>Manage</para>
            </TD>
            <TD>
              <para>View details of your subscription and its expiration date. You can also drill through to purchase or modify your subscription, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Convert a free 30-day trial into a full, paid subscription.</para>
                </listItem>
                <listItem>
                  <para>Buy licenses and add-ons, like Microsoft Desktop Optimization Pack, or buy extra cloud storage space.</para>
                </listItem>
                <listItem>
                  <para>Set up an authorized partner.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Licenses</para>
            </TD>
            <TD>
              <para>View how many licenses you have available.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Purchase</para>
            </TD>
            <TD>
              <para>Manage your subscription, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Convert a free, 30-day trial into a full, paid subscription.</para>
                </listItem>
                <listItem>
                  <para>Buy licenses and add-ons.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Software</para>
            </TD>
            <TD>
              <para>View the software you have bought from Microsoft Online Services on the Microsoft Online Services Customer Portal.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="3">
              <para>Support</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>This page contains a link to TechNet forums for <token>wit_firstref</token>.</para>
              <para>You can also manage <ui>delegated administrators</ui> who are Microsoft Certified Partners for Microsoft cloud services and who manage your subscription on your behalf. If you do not use a partner to manage your subscription, you do not use delegated administrators.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Service Requests</para>
            </TD>
            <TD>
              <para>Find details for getting support by phone or by email.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Service Health</para>
            </TD>
            <TD>
              <para>View the status of the <token>wit_nextref</token> service.</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section>
  <section address="BKMK_AdministratorConsole">
    <title address="BKMK_AdminConsole">Microsoft Intune Administrator console</title>
    <content>
      <para>The <externalLink><linkText>Microsoft Intune Administrator console</linkText><linkUri>https://admin.manage.microsoft.com/</linkUri></externalLink> is where service administrators manage day-to-day tasks for <token>wit_firstref</token>. These tasks include but are not limited to deploying software, managing Endpoint Protection and software updates, configuring policy, and monitoring the devices you manage.</para>
      <para>A service administrator has either <ui>Full access</ui> or <ui>Read-only access</ui> to all objects and pages in the administration console. Any service administrator with full access permissions can manage the permissions of other service administrators.</para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <thead>
          <tr>
            <TD>
              <para>Workspace</para>
            </TD>
            <TD>
              <para>Page</para>
            </TD>
            <TD>
              <para>Details</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>Dashboard</para>
            </TD>
            <TD>
              <para>Not applicable</para>
            </TD>
            <TD>
              <para>The dashboard provides a quick way to assess the health and status of your Intune subscription. Tiles appear and display status and information about the features and configurations you use. When you click on a tile for more information, you are taken to the overview page for that node of the console where more information is available.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="3">
              <para>Groups</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details to identify and prioritize issues that require your immediate attention, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Device health</para>
                </listItem>
                <listItem>
                  <para>Status for alerts, updates, and Endpoint Protection</para>
                </listItem>
                <listItem>
                  <para>Policy issues</para>
                </listItem>
                <listItem>
                  <para>Software status</para>
                </listItem>
              </list>
              <para>You can also create new groups and run reports for hardware inventory.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Users</para>
            </TD>
            <TD>
              <para>View and manage users that have permission to use the subscription, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Create groups of users.</para>
                </listItem>
                <listItem>
                  <para>View details about users and groups of users.</para>
                </listItem>
                <listItem>
                  <para>View and manage the device associations for users.</para>
                </listItem>
              </list>
              <para>To add a new user or grant a license to use the subscription, use the <ui>Users</ui> page in the <ui>Management</ui> node of the <token>wit_firstref</token> account portal.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Devices</para>
            </TD>
            <TD>
              <para>View and manage the devices that are enrolled with your subscription, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Create groups of devices.</para>
                </listItem>
                <listItem>
                  <para>View details about the device, and view groups that include the device.</para>
                </listItem>
                <listItem>
                  <para>Associate users with devices.</para>
                </listItem>
                <listItem>
                  <para>Retire or wipe devices.</para>
                </listItem>
                <listItem>
                  <para>Run <ui>Remote Tasks</ui> on devices.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD rowspan="2">
              <para>Updates</para>
              <para>(This node is available only when you manage computers)</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details for <ui>Update status</ui> and <ui>Cloud Storage status</ui> to identify and prioritize issues that require your immediate attention.</para>
              <para>You can also select <ui>Upload</ui> to start the <ui>Microsoft Intune Software Publisher</ui> to deploy non-Microsoft updates with <token>wit_nextref</token>.</para>
              <para>This page also links to common tasks including:</para>
              <list class="bullet">
                <listItem>
                  <para>Select classifications and products for updates in the <ui>Administration</ui> node of this console.</para>
                </listItem>
                <listItem>
                  <para>Configure <ui>Automatic Approval Settings</ui> in the <ui>Administration</ui> node of this console.</para>
                </listItem>
                <listItem>
                  <para>View reports for updates.</para>
                </listItem>
              </list>
              <para>For information about update management, see <link xlink:href="64ba8e58-fab1-4480-a440-164268810138">Keep your computers up to date with software updates in Microsoft Intune</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Updates</para>
            </TD>
            <TD>
              <para>Manage which updates you plan to deploy to computers, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Approve or decline updates for deployment.</para>
                </listItem>
                <listItem>
                  <para>Select <ui>Upload</ui> to start the <ui>Microsoft Intune Software Publisher</ui> to deploy non-Microsoft updates with <token>wit_nextref</token>.</para>
                </listItem>
                <listItem>
                  <para>View details about updates including which computers need or have an update, and computers that have failed to install an update.</para>
                </listItem>
                <listItem>
                  <para>Access additional information about an update from Microsoft.com.</para>
                </listItem>
              </list>
              <para>By default, <ui>Non-Microsoft Updates</ui> and <ui>Mandatory Updates</ui> always appear, even if there are no updates available in those categories. Other classifications appear only after you enable those classifications in the <ui>Updates</ui> page of the <ui>Administration</ui> workspace of the <token>wit_firstref</token> administrator console.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="2">
              <para>Protection</para>
              <para>(This node is available only when you manage computers)</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details for Endpoint Protection to identify and prioritize issues that require your immediate attention, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Current malware and computer status</para>
                </listItem>
                <listItem>
                  <para>Top malware instances in your environment</para>
                </listItem>
                <listItem>
                  <para>Links to relevant Microsoft Malware Protection Center topics</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Malware</para>
            </TD>
            <TD>
              <para>Manage tasks for protecting your computers and for investigating malware that was found on computers in your environment, including:</para>
              <list class="bullet">
                <listItem>
                  <para>View the status of malware threats in your environment.</para>
                </listItem>
                <listItem>
                  <para>Initiate quick and full scans for malware.</para>
                </listItem>
                <listItem>
                  <para>Update malware definitions on computers.</para>
                </listItem>
                <listItem>
                  <para>Learn more about specific malware.</para>
                </listItem>
              </list>
              <para>For information about configuring Endpoint Protection for computers and scheduling automatic scans, see <link xlink:href="682a83ec-bcf4-46ed-9a74-61b87b6a86a3">Help Secure Your Computers with Endpoint Protection and Windows Firewall Policy for Microsoft Intune</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="2">
              <para>Alerts</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level summaries for alerts to assess the overall health of managed computers in your organization.</para>
              <para>This page also links to common tasks, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Configuring alert types.</para>
                </listItem>
                <listItem>
                  <para>Configuring notification rules.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Alerts</para>
            </TD>
            <TD>
              <para>Manage details for alerts, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Configure alert types.</para>
                </listItem>
                <listItem>
                  <para>Close or reactivate alerts.</para>
                </listItem>
                <listItem>
                  <para>View troubleshooting information when it’s available.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD rowspan="3">
              <para>Apps</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details for software status.</para>
              <para>This page also links to common tasks including:</para>
              <list class="bullet">
                <listItem>
                  <para>Start the <ui>Add Software – Microsoft Intune Software Publisher</ui> to prepare software for deployment to devices.</para>
                </listItem>
                <listItem>
                  <para>View <ui>Managed Software</ui>.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Detected Software</para>
            </TD>
            <TD>
              <para>View a list of the software that <token>wit_nextref</token> detected on computers that you manage.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Apps</para>
            </TD>
            <TD>
              <para>Manage software you deploy to computers and mobile devices, for example:</para>
              <list class="bullet">
                <listItem>
                  <para>Deploy software as a package as a link to a web-based application or as a Windows Store app.</para>
                </listItem>
                <listItem>
                  <para>Configure automatic deployments.</para>
                </listItem>
                <listItem>
                  <para>Modify or delete managed software.</para>
                </listItem>
              </list>
              <para>For more information about deploying software, see <link xlink:href="2b770f4f-6d36-41e4-b535-514b46e29aaa">Prepare for software deployment with Microsoft Intune</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="2">
              <para>Licenses</para>
              <para>(This node is available  only when you manage computers)</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details for the software license agreements you have added to <token>wit_firstref</token>.</para>
              <para>This page also links to common tasks, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Add Microsoft Software License Terms information to the <externalLink><linkText>Microsoft Volume Licensing Service Center (VLSC)</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=223842</linkUri></externalLink> site.</para>
                </listItem>
                <listItem>
                  <para>Add and track license or software agreement information for Microsoft and non-Microsoft software that was purchased by other means.</para>
                </listItem>
                <listItem>
                  <para>Compare the entitlement information that <token>wit_nextref</token> retrieves from VLSC to the inventory of Microsoft software that <token>wit_nextref</token> detects on your managed computers.</para>
                </listItem>
                <listItem>
                  <para>Create custom license groups to organize the view of your licenses.</para>
                </listItem>
                <listItem>
                  <para>View license reports.</para>
                </listItem>
              </list>
              <para>For more information, see <link xlink:href="c59d8635-3f66-40f5-824a-a71c738e0341">Manage license agreements for computer software in Microsoft Intune</link>.</para>
              <alert class="tip">
                <para>Use the <token>wit_firstref</token> account portal to manage <token>wit_nextref</token> licenses </para>
              </alert>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>All Agreements</para>
            </TD>
            <TD>
              <para>Manage details for software licenses you have added to <token>wit_nextref</token>.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="7">
              <para>Policy</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details for policy issues to identify and prioritize issues that require your immediate attention.</para>
              <para>This page also links to common tasks including:</para>
              <list class="bullet">
                <listItem>
                  <para>Add new policies.</para>
                </listItem>
                <listItem>
                  <para>View the list of policies you already have.</para>
                </listItem>
              </list>
              <para>For information about using policies, see <externalLink><linkText>Manage computers with Microsoft Intune</linkText><linkUri>https://technet.microsoft.com/library/dn646989.aspx</linkUri></externalLink>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Policy Conflicts</para>
            </TD>
            <TD>
              <para>Manage policy conflicts, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Identify conflicting policy settings.</para>
                </listItem>
                <listItem>
                  <para>View recommended actions.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Configuration Policies</para>
            </TD>
            <TD>
              <para>Manage configuration policies, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Define or add new policies, and edit or delete policies</para>
                </listItem>
                <listItem>
                  <para>Deploy policies to groups of users or devices</para>
                </listItem>
                <listItem>
                  <para>View information about policies you previously created.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Compliance Policies</para>
            </TD>
            <TD>
              <para>Configure polices that define the compliance level that is required by devices to access specific Office 365 services, like Exchange.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Conditional Access</para>
            </TD>
            <TD>
              <para>Configure polices that manage access to specific Office 365 services, like Exchange, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Define when devices that are not compliant with a compliance policy are blocked or exempted from accessing services</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Exchange ActiveSync</para>
            </TD>
            <TD>
              <para>Configure access rules for devices connecting to Exchange or Exchange Online that are not managed by <token>wit_nextref</token>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Corporate Device Enrollment</para>
            </TD>
            <TD>
              <para>Apply a one-time configuration for company owned devices during enrollment. This lets you configure enrollment settings such as initial device group affiliation and user association.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="11">
              <para>Reports</para>
            <para>(This node is available  only when you manage computers)</para></TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View descriptions of the different report categories.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Update Reports</para>
            </TD>
            <TD>
              <para>Manage reports about updates, by device, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>Update classifications and status</para>
                </listItem>
                <listItem>
                  <para>Microsoft Security Response Center (MSRC) rating</para>
                </listItem>
                <listItem>
                  <para>Effective approval</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Detected Software Reports</para>
            </TD>
            <TD>
              <para>Manage reports about software in your environment, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>Device group</para>
                </listItem>
                <listItem>
                  <para>Publisher</para>
                </listItem>
                <listItem>
                  <para>Categories</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Computer Inventory Reports</para>
            </TD>
            <TD>
              <para>Manage reports about hardware installed on computers in your environment, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>Device groups</para>
                </listItem>
                <listItem>
                  <para>Operating systems</para>
                </listItem>
                <listItem>
                  <para>Manufacture and models</para>
                </listItem>
                <listItem>
                  <para>Disk space, memory, and processor speed</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Mobile Device Inventory reports</para>
            </TD>
            <TD>
              <para>Manage reports about the mobile devices in your environment, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>Device groups</para>
                </listItem>
                <listItem>
                  <para>Operating systems</para>
                </listItem>
                <listItem>
                  <para>Jail-broken or rooted devices</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>License Purchase Reports</para>
            </TD>
            <TD>
              <para>Manage reports about licenses, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>License type</para>
                </listItem>
                <listItem>
                  <para>License groups</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>License Installation Reports</para>
            </TD>
            <TD>
              <para>Manage reports about the software that is in the Software Asset Catalog for which you have license details, including criteria for:</para>
              <list class="bullet">
                <listItem>
                  <para>License type</para>
                </listItem>
                <listItem>
                  <para>License groups</para>
                </listItem>
                <listItem>
                  <para>Device groups</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Terms and Conditions Reports</para>
            </TD>
            <TD>
              <para>View details about users who accepted your terms and conditions.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Noncompliance Apps Reports</para>
            </TD>
            <TD>
              <para>Manage reports for non-compliant users and devices for app policies.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Certificate Compliance Reports</para>
            </TD>
            <TD>
              <para>Configure report criteria and then view a report for certificate compliance.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Device History Reports</para>
            </TD>
            <TD>
              <para>View historical details for retire, wipe and delete actions you have managed in the last 90 days.</para>
            </TD>
          </tr>
          <tr>
            <TD rowspan="8">
              <para>Administration</para>
            </TD>
            <TD>
              <para>Overview</para>
            </TD>
            <TD>
              <para>View high-level details of your service, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Details about your subscription</para>
                </listItem>
                <listItem>
                  <para>Details about your cloud storage</para>
                </listItem>
                <listItem>
                  <para>Links to check the status of the service</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Updates</para>
            <para>(This node is available  only when you manage computers)</para></TD>
            <TD>
              <para>Configure settings for managing updates, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Product categories to synchronize</para>
                </listItem>
                <listItem>
                  <para>Update classifications</para>
                </listItem>
                <listItem>
                  <para>Automatic Approval Rules</para>
                </listItem>
              </list>
              <para>For more information, <link xlink:href="64ba8e58-fab1-4480-a440-164268810138">Keep your computers up to date with software updates in Microsoft Intune</link>.</para>
              <para>To approve or decline updates, use the <ui>All Updates</ui> page of the <ui>Updates</ui> workspace.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Alerts and Notifications</para>
            </TD>
            <TD>
              <para>Manage alerts, including the following:</para>
              <list class="bullet">
                <listItem>
                  <para>Enable or disable alert types you want to view.</para>
                </listItem>
                <listItem>
                  <para>Set alert thresholds.</para>
                </listItem>
                <listItem>
                  <para>Set up email notification for alerts.</para>
                </listItem>
              </list>
              <para>For more information, see <link xlink:href="396ea714-0433-4bd5-a934-8d0b477f28e4">Configure Alerts in Microsoft Intune</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Administrator Management</para>
            </TD>
            <TD>
              <para>View and manage administrator accounts, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Add and manage existing service administrators.</para>
                </listItem>
                <listItem>
                  <para>View a list of tenant administrators, service administrators, or device enrollment manager.</para>
                </listItem>
                <listItem>
                  <para>Assign users to be device enrollment managers</para>
                </listItem>
              </list>
              <para>For more information, see <ui>Microsoft Intune administrator accounts</ui> in this topic.</para>
              <para>For information about configuring administrator accounts, see <link xlink:href="d158503c-1276-422b-ab81-5f66c1cd7e7a#BKMK_AssignAdmins">Task 5: Assign administrative users</link> in the <link xlink:href="d158503c-1276-422b-ab81-5f66c1cd7e7a">Set up Microsoft Intune</link> topic.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Client Software Download</para>
            </TD>
            <TD>
              <para>Manage the <token>wit_nextref</token> client, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Tasks to complete prior to deploying the client software</para>
                </listItem>
                <listItem>
                  <para>Download and deploy the client software.</para>
                </listItem>
                <listItem>
                  <para>Tasks to complete after you deploy the client software.</para>
                </listItem>
              </list>
              <para>For more information, see <link xlink:href="64c11e53-8d64-41b9-9550-4b4e395e8c52">Set up Your Computers to be Managed by Microsoft Intune</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Storage Use</para>
            </TD>
            <TD>
              <para>Manage and review your use of your cloud storage:</para>
              <list class="bullet">
                <listItem>
                  <para>View the amount of cloud storage you have available.</para>
                </listItem>
                <listItem>
                  <para>View a list of applications and updates that are stored in your cloud storage.</para>
                </listItem>
                <listItem>
                  <para>Delete objects from your cloud storage.</para>
                </listItem>
              </list>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Mobile Device Management</para>
            </TD>
            <TD>
              <para>Manage mobile devices, including:</para>
              <list class="bullet">
                <listItem>
                  <para>Set <link xlink:href="5d1ac59c-a885-4276-8576-f3cf81c2d268#BKMK_MDMA">Mobile Device Management Authority</link> to be <token>wit_firstref</token>.</para>
                </listItem>
                <listItem>
                  <para>Upload required certificates for mobile devices.</para>
                </listItem>
                <listItem>
                  <para>Download and deploy company portal apps.</para>
                </listItem>
                <listItem>
                  <para>Download a connector for Exchange ActiveSync.</para>
                </listItem>
              </list>
              <para>For more information, see <link xlink:href="44fd4af0-f9b0-493a-b590-7825139d9d40#BKMK_MDMAuth">Prepare for mobile device management</link>.</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Company Portal</para>
            </TD>
            <TD>
              <para>Customize your information for the <token>wit_firstref</token> company portal.</para>
              <para>For more information, see <link xlink:href="d158503c-1276-422b-ab81-5f66c1cd7e7a#BKMK_ConfigureCompanyPortal">Task 7: Customize the Company Portal</link>.</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section>
  <relatedTopics/>
</developerWalkthroughDocument>
