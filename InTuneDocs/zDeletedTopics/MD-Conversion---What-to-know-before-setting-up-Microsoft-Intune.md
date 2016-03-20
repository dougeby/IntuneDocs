---
title: MD Conversion - What to know before setting up Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 55112a2a-ccee-499f-975a-40a1b89e080f
---
# MD Conversion - What to know before setting up Microsoft Intune
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Before you set up <token>wit_firstref</token>, you might want to review <link xlink:href="1bfd1a23-681d-4cc8-834c-c7856d69d409">Evaluate Microsoft Intune</link>. After you are familiar with the capabilities of <token>wit_nextref</token>, you should be ready to set up your subscription. If you start with a trial subscription, at a later time you can convert it to a full subscription. To convert a trial subscription, see <externalLink><linkText>How to buy Intune</linkText><linkUri>http://technet.microsoft.com/library/dn646949.aspx</linkUri></externalLink>.</para>
    <para>This topic includes information about:</para>
    <list class="bullet">
      
      <listItem>
        <para>
          <externalLink>
            <linkText>Supported browsers</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers</linkUri>
          </externalLink>
        </para>
      </listItem><listItem>
        <para>
          <externalLink>
            <linkText>Administrative accounts and permissions for separate tasks</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_AdminAccounts</linkUri>
          </externalLink>
        </para>
      </listItem><listItem>
        <para>
          <externalLink>
            <linkText>Web-based portals for administrative tasks</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_AdminWebsites</linkUri>
          </externalLink>
        </para>
      </listItem>
      <listItem>
        <para>
          <externalLink>
            <linkText>Company portal website or app for users</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal</linkUri>
          </externalLink>
        </para>
      </listItem>
      
      <listItem>
        <para>
          <externalLink>
            <linkText>How Intune interacts with other Microsoft services</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_ServiceIntegration</linkUri>
          </externalLink>
        </para>
      </listItem>
      <listItem>
        <para>
          <externalLink>
            <linkText>How Intune interacts with other Microsoft products</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_ProdcutIntegration</linkUri>
          </externalLink>
        </para>
      </listItem>
      <listItem>
        <para>
          <externalLink>
            <linkText>The amount of network bandwidth use you can expect</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_NetworkBandwidth</linkUri>
          </externalLink>
        </para>
      </listItem>
      <listItem>
        <para>
          <externalLink>
            <linkText>Choosing a domain name you will use</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_DomainNames</linkUri>
          </externalLink>
        </para>
      </listItem>
      <listItem>
        <para>
          <externalLink>
            <linkText>How Intune maintains security of your data</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_DataSecurity</linkUri>
          </externalLink>
        </para>
      </listItem>
    </list>
  </introduction>
  <section DoNotNumber="true">
<title>Core concepts in Microsoft  Intune</title><content><para><token>wit_nextref</token> has the following general capabilities:</para><list class="nobullet">
        <listItem>
          <para>
            <embeddedLabel>Manage mobile devices and computers, no servers or intranet required.</embeddedLabel> You can manage mobile devices and computers, even if those devices are not joined to a domain or brought on-site. This makes <token>wit_nextref</token> ideal for a company with a mobile or geographically-distributed workforce.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Require encryption of mobile devices and computers.</embeddedLabel> Mobile devices that support encryption can be required to use it. You can also require computers that support Bitlocker drive encryption to use it. If a mobile device or computer with encryption is lost or stolen, the data on the device’s storage media is unreadable, helping to secure that data it from theft. </para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Generate hardware and software inventories and reports.</embeddedLabel> You can gather information on the hardware and software used by your company, helping you to plan your hardware upgrade cycle or determine if unwanted software is installed on managed devices.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Monitor mobile devices and computers.</embeddedLabel> You can create alerts to notify you when there is a problem with a mobile device or a computer, and also have alerts trigger e-mail notifications so that the right people are informed of the problem.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Provide a “self-service” model for IT.</embeddedLabel> Users can use the company portal to enroll devices, to install site-licensed software, or to find contact information for IT administrators.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Support multi-factor authentication. </embeddedLabel> <token>wit_nextref</token> now supports multi-factor authentication. For details, see <link xlink:href="9b4f197d-bc10-4bee-91c9-19bcc8287d36">Use multifactor authentication in Microsoft Intune</link>.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>Available in multiple languages.</embeddedLabel> Intune is now available in the following languages: Chinese (Simplified and Traditional), Czech, Danish, Dutch, English, Finnish, French, German, Greek, Hungarian, Italian, Japanese, Korean, Norwegian, Polish, Portuguese, Romanian, Russian, Spanish, Swedish, Turkish.  For a list of the countries where the <token>wit_nextref</token> service is supported, see <externalLink><linkText>International availability</linkText><linkUri>https://products.office.com/en-us/business/international-availability</linkUri></externalLink>.</para>
          
        </listItem>
      </list>
      
      </content>
</section><section address="BKMK_SupportedBrowsers">
    <title>Web browser requirements</title>
    <content>
      <para>The following web browsers are supported.</para>
      <table>
        <thead>
          <tr>
            <TD>
              <para>Platform</para>
            </TD>
            <TD>
              <para>Minimum browser version</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>Mobile device platforms</para>
            </TD>
            <TD>
              <para>The Microsoft Intune company portal website is supported by the default web browser for each supported platform. </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Windows computers</para>
            </TD>
            <TD>
              <?Comment BD: Last revision H: Bug 134903 2014-12-18T11:30:00Z  Id='122?>
              <para>The following web browsers are supported for use with the <token>wit_icp_1</token>, <token>wit_adminconsole</token>, and the <token>wit_iwportal_1</token> website:</para>
              
                  <para><ui>Internet Explorer 9 or later</ui> </para>

                  <para><ui>Google Chrome</ui> (versions prior to version 42)</para>
            
                  <para><ui>Mozilla Firefox</ui></para>
                  <para>Starting in February, 2016, Internet Explorer 9 will no longer be supported as an official browser for accessing the Microsoft Intune company portal website, Intune account portal, and Intune administration console. You will need to migrate to Internet Explorer 10 or later.</para>
             
            </TD>
          </tr><tr><TD><para>Mac OS X</para></TD><TD><para>The Microsoft Intune Company Portal website is supported by Safari browser on Mac OS X 10.9 or later.</para></TD></tr>
        </tbody>
      </table>
    </content>
  </section><section address="BKMK_AdministrativeTasks">
    <title>How Intune divides administrative tasks</title>
    <content>
      <para>You use two types of administrator accounts, user accounts with additional permissions, and two separate administration consoles to grant your admins access to the things they should manage. The following sections explain these accounts and portals.</para>
    </content>
    <sections>
      <section address="BKMK_AdminAccounts" expanded="false">
        <title> Intune administrator accounts and special permissions</title>
        <content>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>Account type</para>
                </TD>
                <TD>
                  <para>Permission levels</para>
                </TD>
                <TD>
                  <para>More information</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>Tenant administrator</embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage. </para>
                  <para>Administrator roles are common between the different Microsoft cloud services although some services might not support some roles. <token>wit_nextref</token> uses the following roles:</para>
                 
                      <para><ui>Global administrator</ui></para>
                  
                      <para><ui>Billing administrator</ui></para>
                   
                      <para><ui>Password administrator</ui></para>
                  
                      <para><ui>Service support administrator</ui></para>
                   
                      <para><ui>User management administrator</ui></para>
                   
                  <para>Learn more about administrator roles: <link xlink:href="e4eff7b9-4dcd-4959-b1d6-97dc4640dbe2">Reference for Tenant Administrator accounts for Microsoft Intune</link>.</para>
                  <para> <externalLink><linkText>Assign administrative users</linkText><linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_AssignAdmins</linkUri></externalLink>.</para>
                </TD>
                <TD>
                  <para>By default, the account you use to create your <token>wit_nextref</token> subscription is a tenant administrator with the global administrator role.
                        <embeddedLabel>As a tenant administrator, you use the <token>wit_icp_1</token> to manage your subscription for <token>wit_nextref</token>.</embeddedLabel> and assign tenant administrators from within the <token>wit_icp_2</token>.</para>
                  
                      <para>Use a tenant administrator with the global administration role to access the <token>wit_adminconsole</token> to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to <token>wit_nextref</token> to access the <token>wit_icp_2</token>.</para>
                   
                  <para>The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to <token>wit_nextref</token>, your service is a <externalLink><linkText>tenant of Microsoft Azure AD</linkText><linkUri>http://technet.microsoft.com/library/jj573650.aspx</linkUri></externalLink>. </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>Service administrator</embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>Service administrators are assigned one of the following permissions:</para>
                 
                      <para>
                        <ui>Full access</ui>: Grants access to all areas of the <token>wit_adminconsole</token>, with no restrictions. Can also add and manage other service administrators.</para>
                   
                      <para>
                        <ui>Read-only access</ui>: Grants read permission to all areas of the <token>wit_adminconsole</token>. A read-only service admin cannot modify data, but can run reports.</para>
                  
                      <para>
                        <embeddedLabel>Helpdesk - Groups Node</embeddedLabel>: Grants permissions that enable the service administrator to only perform a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see <link xlink:href="e0783eaa-67dc-410e-9e80-4d3aa72f36d8">Manage access levels in the Microsoft Intune admin console</link>.</para>
                  
                  <para>
                    <externalLink>
                      <linkText>Assign administrative users</linkText>
                      <linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_AssignAdmins</linkUri>
                    </externalLink>
                  </para>
                </TD>
                <TD>
                  <para>By default, <token>wit_nextref</token> does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. <embeddedLabel>As a service administrator, you use the <token>wit_adminconsole</token> to manage day-to-day tasks for <token>wit_nextref</token></embeddedLabel>.</para>
                   
                      <para>You assign service administrators from within the administrator console. A service administrator requires a license to <token>wit_nextref</token> before the account can access the administration console. </para>
                   
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>Device enrollment manager</embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>Device enrollment managers are standard user accounts that have additional permission to enroll more than five devices. </para>
                  <para>
                    <externalLink>
                      <linkText>Learn about device enrollment managers</linkText>
                      <linkUri>http://technet.microsoft.com/library/dn764961.aspx</linkUri>
                    </externalLink>.</para>
                </TD>
                <TD>
                  <para>By default, each <token>wit_firstref</token> user can enroll up to five devices. </para>
                  <para>However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or serve in a kiosk mode where a user to device association is not required.</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section address="BKMK_AdminWebsites" expanded="false">
        <title> Administrative websites for Intune</title>
        <content>
          <para>Different administrative tasks require you to use one of two administrative websites. Because the configurations you make and data from devices that you manage are stored in the cloud, you can manage your subscription from any computer with <externalLink>
            <linkText>a supported browser</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers</linkUri>
          </externalLink>.</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>Administrative website</para>
                </TD>
                <TD>
                  <para>More information</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>Microsoft Intune account portal</linkText>
                      <linkUri>http://go.microsoft.com/fwlink/p/?LinkId=698854</linkUri>
                    </externalLink>
                  </para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>As a tenant administrator, use this portal to manage your subscription</embeddedLabel>, including the following tasks when permitted by your administrator role:</para>
                  
                      <para>Manage user accounts for the subscription and configure directory synchronization from your on-premises Active Directory.</para>
                  
                      <para>Manage groups of users, called security groups.</para>
                   
                      <para>Assign licenses to use <token>wit_nextref</token> to users.</para>
                   
                      <para>Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with. </para>
                    
                      <para>Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.</para>
                    
                      <para>Find links to view the health of the <token>wit_nextref</token> service.</para>
                   
                  <para>As a tenant administrator, you can sign in to the account portal to manage the subscription even when your account is not assigned a license to use <token>wit_nextref</token>.</para>
                  <para>Any user who has a license to <token>wit_nextref</token> but is not an administrator can use this portal to reset their account password and edit their profile.</para>
                  <para>To access the account portal, your account must have a sign-in status of <ui>Allowed</ui>. This status is distinct from being granted a license to the subscription. By default, all user accounts are <ui>Allowed</ui>. </para>
                  <para>Learn more about <externalLink><linkText>adding users and assigning licenses for your subscription</linkText><linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses</linkUri></externalLink>.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>Microsoft Intune administrator console</linkText>
                      <linkUri>https://admin.manage.microsoft.com/</linkUri>
                    </externalLink>
                  </para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>As a service administrator, use this portal to manage day-to-day operations</embeddedLabel> including:</para>
                 
                      <para>Set policies for computers and mobile devices.</para>
                   
                      <para>Upload and deploy software like software updates and apps.</para>
                   
                      <para>Manage <token>wit_nextref</token> Endpoint Protection on computers.</para>
                   
                      <para>View device status and run reports.</para>
                   
                  <para>A user who does not have service administrator permissions cannot sign in to this portal. An exception to this restriction is a user who is a tenant administrator with the global administrator role.</para>
                  <para>To access the administration console, your account must have a license to use <token>wit_nextref</token> and a sign-in status of <ui>Allowed</ui>. By default, all user accounts are set to <ui>Allowed</ui>. </para>
                  <para>Learn more about <externalLink><linkText>adding users and assigning licenses for your subscription</linkText><linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses</linkUri></externalLink>.</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
    </sections>
  </section>
  <section address="BKMK_CompanyPortal" expanded="true">
    <title>Microsoft Intune company portal</title>
    <content>
      <para>The <token>wit_iwportal_1</token> provides users access to company data and apps. Users can access the company portal by using:</para>
      <list class="bullet">
        <listItem>
          <para>
            <embeddedLabel>The company portal app</embeddedLabel>: An application that is available on devices you manage with <token>wit_nextref</token>. This company portal is also called a self-service portal.</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>The company portal website</embeddedLabel>: A website that provides access from <externalLink>
            <linkText>a supported browser</linkText>
            <linkUri>http://technet.microsoft.com/library/dn646966.aspx#BKMK_SupportedBrowsers</linkUri>
          </externalLink>.</para>
        </listItem>
      </list>
      <para>Users can use the <token>wit_iwportal_2</token> to:</para>
      <list class="bullet">
        <listItem>
          <para>Enroll devices</para>
        </listItem>
        <listItem>
          <para>View the status of their devices</para>
        </listItem>
        <listItem>
          <para>Download software that is deployed by your organization</para>
        </listItem>
        <listItem>
          <para>Contact your IT department for support</para>
        </listItem>
      </list>
      <para>Before a user can access the <token>wit_iwportal_2</token>, the user’s account must be granted a license to use <token>wit_nextref</token> and have a sign-in status of <ui>Allowed</ui>. Learn more about <externalLink><linkText>adding users and assigning licenses for your subscription</linkText><linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_AddUsersAssignLicenses</linkUri></externalLink>.</para>
      <para>Following is the ULR for the company portal website. When users sign in, they gain access to your company portal website.</para>
      <list class="bullet">
        <listItem>
          <para>
            <externalLink>
              <linkText>https://portal.manage.microsoft.com</linkText>
              <linkUri>https://portal.manage.microsoft.<?Comment BD: 174432 2015-04-28T09:13:00Z  Id='36?>com<?CommentEnd Id='36'
    ?></linkUri>
            </externalLink>
          </para>
        </listItem>
      </list>
      <para>Learn more about <externalLink><linkText> customizing the company portal</linkText><linkUri>http://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal</linkUri></externalLink>.</para>
    </content>
  </section>
  
  <section address="BKMK_ServiceIntegration">
    <title>Integration with other Microsoft cloud services</title>
    <content>
      <para>
        <token>wit_nextref</token> shares a common foundation with other Microsoft cloud services. When you use the same account to subscribe to multiple cloud services, those services use the same Microsoft Azure AD infrastructure, and they are tenants of Azure AD. Azure AD provides the core directory and identity management capabilities for Microsoft cloud services.</para>
      <para>Learn more about <externalLink><linkText>administering Azure AD </linkText><linkUri>http://technet.microsoft.com/library/hh967611.aspx</linkUri></externalLink> in the TechNet Library.</para>
    </content>
  </section>
  <section address="BKMK_ProdcutIntegration" expanded="false">
    <title>Integration with other Microsoft products</title>
    <content>
      <para>You can use <token>wit_firstref</token> as a stand-alone cloud service or as a cloud service that is integrated with other products. Presently, only <token>cmshort</token> can be integrated directly with <token>wit_nextref</token>.</para>
      <para>The decision to integrate <token>wit_nextref</token> with <token>cmshort</token> is a permanent choice that requires you to set the mobile device management authority from the <token>cmshort</token> console and not from within the <token>wit_icp_1</token>. After the mobile device management authority is set, you cannot change or reverse this configuration.</para>
      <para>When you use <token>wit_nextref</token> with <token>cmshort</token>, you do not use the <token>wit_adminconsole</token> to manage <token>wit_nextref</token> and instead use the <token>cmshort</token> console. <token>wit_nextref</token> still uses its cloud storage in Azure to host software that you deploy to devices that you manage with <token>wit_nextref</token>.</para>
      <para>For more information, see <legacyLink xlink:href="2c6bd0e5-d436-41c8-bf38-30152d76be10">Manage Mobile Devices with Configuration Manager and Microsoft Intune</legacyLink> in the <token>cm5short</token> SP1 documentation.</para>
    </content>
  </section>
  <section address="BKMK_NetworkBandwidth" expanded="false">
    <title>Network bandwidth use</title>
    <content>
      <para>Use the information in the following sections to plan for network traffic for <token>wit_firstref</token> clients.</para>
    </content>
    <sections>
      <section address="BKMK_AverageTraffic">
        <title>Average network traffic</title>
        <content>
          <para>The following table lists the approximate size and frequency of common content that travels across the network for each client.</para>
          <alert class="note">
            <para>To ensure that computers and mobile devices receive the necessary updates and content from the <token>wit_nextref</token> service, they must be periodically connected to the Internet. The time taken to receive updates or content will vary, but as a guideline, they should remain continuously connected to the Internet for at least 1 hour each day.</para>
          </alert>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>Content type</para>
                </TD>
                <TD>
                  <para>Approximate size</para>
                </TD>
                <TD>
                  <para>Frequency and details</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <token>wit_nextref</token> client installation</para>
                </TD>
                <TD>
                  <para>125 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>The size of the client download varies depending on the operating system of the client computer.</para>
                </TD>
              </tr>
              <tr>
                <TD colspan="3">
                  <para>
                    <embeddedLabel>The following requirements are in addition to the <token>wit_nextref</token> client installation</embeddedLabel>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Client enrollment package</para>
                </TD>
                <TD>
                  <para>15 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>Additional downloads are possible when there are updates for this content type.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Endpoint Protection agent</para>
                </TD>
                <TD>
                  <para>65 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>Additional downloads are possible when there are updates for this content type.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Operations Manager agent</para>
                </TD>
                <TD>
                  <para>11 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>Additional downloads are possible when there are updates for this content type.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Policy agent</para>
                </TD>
                <TD>
                  <para>3 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>Additional downloads are possible when there are updates for this content type.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Remote Assistance via Microsoft Easy Assist agent</para>
                </TD>
                <TD>
                  <para>6 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>One time</embeddedLabel>
                  </para>
                  <para>Additional downloads are possible when there are updates for this content type.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Daily client operations</para>
                </TD>
                <TD>
                  <para>6 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Daily</embeddedLabel>
                  </para>
                  <para>The <token>wit_nextref</token> client regularly communicates with the <token>wit_nextref</token> service to check for updates and policies, and to report the client’s status to the service.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Endpoint Protection malware definition updates</para>
                </TD>
                <TD>
                  <para>Varies </para>
                  <para>Typically 40 KB to 2 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Daily</embeddedLabel>
                  </para>
                  <para>Up to three times a day.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Endpoint Protection engine update</para>
                </TD>
                <TD>
                  <para>5 MB</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Monthly</embeddedLabel>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para> Software updates</para>
                </TD>
                <TD>
                  <para>Varies </para>
                  <para>The size depends on the updates you deploy.</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Monthly</embeddedLabel>
                  </para>
                  <para>Typically, software updates release on the second Tuesday of each month.</para>
                  <para>A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Service packs</para>
                </TD>
                <TD>
                  <para>Varies </para>
                  <para>The size varies for each service pack you deploy. </para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Varies</embeddedLabel>
                  </para>
                  <para>Depends on when you deploy service packs.</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Software distribution</para>
                </TD>
                <TD>
                  <para>Varies </para>
                  <para>The size depends on the software you deploy.</para>
                </TD>
                <TD>
                  <para>
                    <embeddedLabel>Varies</embeddedLabel>
                  </para>
                  <para>Depends on when you deploy software. </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      <sections><section address="BKMK_ReduceBandwidth">
        <title>Reduce network bandwidth use</title>
        <content>
          <para>You can use one or more of the following methods to reduce network bandwidth use for <token>wit_nextref</token> clients.</para>
        </content>
        <sections>
          <section address="BKMK_UseProxy" expanded="false">
            <title>Use a proxy server to cache content requests</title>
            <content>
              <para>You can use a proxy server that can cache content to reduce duplicate downloads and reduce the use of network bandwidth by clients that request content from the Internet.</para>
              <para>A caching proxy server receives requests for content from client computers on your network, retrieves that content from the Internet, and can then cache both HTTP responses and binary downloads. The server uses the cached information to answer subsequent requests from <token>wit_nextref</token> client computers.</para>
              <para>The following are typical settings to use for a proxy server that caches content for <token>wit_nextref</token> clients.</para>
              <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
                <thead>
                  <tr>
                    <TD>
                      <para>Setting</para>
                    </TD>
                    <TD>
                      <para>Recommended value</para>
                    </TD>
                    <TD>
                      <para>Details</para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>Cache size</para>
                    </TD>
                    <TD>
                      <para>5 GB to 30 GB</para>
                    </TD>
                    <TD>
                      <para>The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>Individual cache file size</para>
                    </TD>
                    <TD>
                      <para>950 MB</para>
                    </TD>
                    <TD>
                      <para>This setting might not be available in all caching proxy servers.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>Object types to cache</para>
                    </TD>
                    <TD>
                      <para>HTTP</para>
                      <para>HTTPS</para>
                      <para>BITS</para>
                    </TD>
                    <TD>
                      <para>
                        <token>wit_nextref</token> packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.</para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>For information about using a proxy server to cache content, see the documentation for your proxy server solution.</para>
            </content>
          </section>
          <section address="BKMK_UseBITS" expanded="false">
            <title>Use Background Intelligent Transfer Service on computers</title>
            <content>
              <para>
                <token>wit_firstref</token> supports using Background Intelligent Transfer Service (BITS) on a Windows computer to reduce the network bandwidth that is used during the hours that you configure. You can configure policy for BITS on the <ui>Network bandwidth</ui> page of the <token>wit_nextref</token> Agent policy.</para>
              <para>To learn more about BITS and Windows computers, see <externalLink><linkText>Background Intelligent Transfer Service</linkText><linkUri>http://technet.microsoft.com/library/bb968799.aspx</linkUri></externalLink> in the TechNet Library.</para>
            </content>
          </section>
          <section address="BKMK_UseBrancCache" expanded="false">
            <title>Use BranchCache on computers</title>
            <content>
              <para>
                <token>wit_nextref</token> clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems that are supported as clients also support BranchCache:</para>
              <list class="bullet">
                <listItem>
                  <para>
                    <token>nextref_client_7</token>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <token>win8_client_2</token>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <token>winblue_client_2</token>
                  </para>
                </listItem>
              </list>
              <para>To use BranchCache, the client computer must have BranchCache enabled, and then be configured for <ui>distributed cache mode</ui>.</para>
              <para>By default, BranchCache and distributed cache mode are enabled on a computer when the <token>wit_nextref</token> client is installed. However, if the client already has Group Policy that disables BranchCache, <token>wit_nextref</token> does not override that policy and BranchCache will remains disabled on that computer.</para>
              <para>If you use BranchCache, you should communicate with other administrators in your organization who manage Group Policy and <token>wit_firstref</token> Firewall policy to ensure they do not deploy policy that disables BranchCache or Firewall exceptions.</para>
              <para>Learn more: <externalLink><linkText>BranchCache Overview</linkText><linkUri>http://technet.microsoft.com/library/hh831696.aspx</linkUri></externalLink>.</para>
            </content>
          </section>
        </sections>
      </section></sections></section>
      
    </sections>
  </section>
  <section address="BKMK_DomainNames">
    <title address="BKMK_DomainName">Domain names for Microsoft Intune</title>
    <content>
      <para>When your organization signs up for a cloud-based service from Microsoft like <token>wit_firstref</token>, you’re given an initial domain name that looks like the following: <userInput>contoso.onmicrosoft.com</userInput>. In this example, <userInput>contoso</userInput> is the domain name that you chose when you signed up, and <embeddedLabel>onmicrosoft.com</embeddedLabel> is the suffix assigned to accounts you add to your subscription. After you complete the sign-up process, you cannot change that domain name. However, as a global administrator, you can add your own custom domain names for your organization to use with the service, or you can remove domains that you’ve added previously.</para>
      <para>By default, when you use the onmicrosoft domain, each user you import receives the <embeddedLabel>onmicrosoft.com</embeddedLabel> suffix for their user principal name (UPN).</para>
      <para>If you want to use a domain name that you own rather than the one that you were given at signup, you can add the domain name to Azure AD. After you add the domain, and it has been verified that you own it, you can create accounts and groups that include the domain name by changing DNS resource records at your DNS hosting provider. To simplify management of user accounts when you plan to use a custom domain, <link xlink:href="d158503c-1276-422b-ab81-5f66c1cd7e7a#BKMK_ConfigureDomain">add the custom domain name</link> to your subscription before you begin to synchronize users from your local Active Directory.</para>
      <para>Because the information about configuring domain names and DNS resource records for <token>wit_nextref</token> is the same as for other Azure AD tenants, use the information and procedures found under <externalLink><linkText>Internet domain management</linkText><linkUri>http://technet.microsoft.com/library/hh969248.aspx</linkUri></externalLink>, which include:</para>
      <list class="bullet">
        <listItem>
          <para>
            <externalLink>
              <linkText>Add your domain</linkText>
              <linkUri>http://technet.microsoft.com/library/hh969247.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
        <listItem>
          <para>
            <externalLink>
              <linkText>DNS Basics</linkText>
              <linkUri>http://technet.microsoft.com/library/jj151795.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
        <listItem>
          <para>
            <externalLink>
              <linkText>Locate your domain services or buy a new domain</linkText>
              <linkUri>http://technet.microsoft.com/library/jj151801.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
        <listItem>
          <para>
            <externalLink>
              <linkText>Work with domain names and DNS records</linkText>
              <linkUri>http://technet.microsoft.com/library/jj151817.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
        <listItem>
          <para>
            <externalLink>
              <linkText>Verify a domain</linkText>
              <linkUri>http://technet.microsoft.com/library/jj151788.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
        <listItem>
          <para>
            <externalLink>
              <linkText>Troubleshoot issues after changing your domain name</linkText>
              <linkUri>http://technet.microsoft.com/library/jj151793.aspx</linkUri>
            </externalLink>
          </para>
        </listItem>
      </list>
      <para>After you review the information about domains and DNS resource records, return to this topic to continue learning about <token>wit_nextref</token>.</para>
    </content>
  </section>
  <section address="BKMK_DataSecurity">
    <title>Data security with Microsoft Intune</title>
    <content>
      <para>
        <token>wit_nextref</token> is a cloud-based service where the infrastructure that hosts your data is managed for you in Azure datacenters. The cloud-based storage of data can raise a number of questions that often include the following:</para>
      <list class="bullet">
        <listItem>
          <para>Who has access to the data?</para>
        </listItem>
        <listItem>
          <para>Where does <token>wit_nextref</token> store data when using Microsoft Azure?</para>
        </listItem>
        <listItem>
          <para>How is data secured, including transfer between clients, web consoles, and the cloud?</para>
        </listItem>
        <listItem>
          <para>How is the privacy of data assured?</para>
        </listItem>
        <listItem>
          <para>Who owns the data?</para>
        </listItem>
        <listItem>
          <para>Is there any third-party verification?</para>
        </listItem>
      </list>
      <para>These and additional data security questions are answered in the <externalLink><linkText>Microsoft Intune Privacy and Data Protection Overview</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=528219</linkUri></externalLink> white paper.</para>
    </content>
  </section>
  
  <relatedTopics><link xlink:href="3b4e778d-ac13-4c23-974f-5122f74626bc">Overview of Microsoft Intune and core concepts</link><link xlink:href="074de65b-84a5-4a01-a824-18ffd838eab0">Requirements for Microsoft Intune</link></relatedTopics>
</developerWalkthroughDocument>

