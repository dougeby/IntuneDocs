---
title: MD Conversion - Help users connect to their work using VPN profiles with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 39e3b32b-51e6-4da8-9762-f0f4872bf0a9
---
# MD Conversion - Help users connect to their work using VPN profiles with Microsoft Intune
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Virtual Private Networks (VPN) let you give your users secure remote access to your company network. Remote users can work as if their device is physically connected to the network. Devices use a VPN connection profile to initiate a connection with the VPN server. Use <ui>VPN profiles</ui> in <token>wit_firstref</token> to deploy VPN settings to users and devices in your organization. By deploying these settings, you minimize the end-user effort required to connect to resources on the company network.</para>
    <para>For example, you want to provision all iOS devices with the settings required to connect to a file share on the corporate network. You create a VPN profile containing the settings necessary to connect to the corporate network and then deploy this profile to all users with iOS devices. The users will see the VPN connection in the list of available networks and can connect with the minimum of effort.</para>
    <para>You can configure the following device types with VPN profiles:</para>
    <list class="bullet">
      <listItem>
        <para>Devices that run Android 4 and later</para>
      </listItem>
      <listItem>
        <para>Devices that run iOS 7.1 and later</para>
      </listItem>
      <listItem>
        <para>Devices that run Max OS X 10.9 and later</para>
      </listItem>
      <listItem>
        <para>Enrolled devices that run Windows 8.1 and later (includes <?Comment RS: Confirmed with Karan 2014-09-24T14:21:00Z  Id='0?>Windows RT 8.1<?CommentEnd Id='0'
    ?>)</para>
      </listItem>
      <listItem>
        <para>Devices that run Windows Phone 8.1 and later</para>
      </listItem>
    <listItem><para>Devices that run Windows 10 desktop and mobile.</para></listItem></list>
    <para>The VPN profile configuration options will differ depending on the device type you select.</para>
  </introduction>
  <section>
    <title>VPN connection types</title>
    <content>
      <para>
        <token>wit_nextref</token> supports creating VPN profiles that use the following connection types:</para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <tbody>
          <tr>
            <TD>
              <para>
                <ui>Connection type</ui>
              </para>
            </TD>
            <TD>
              <para>
                <ui>iOS and Mac OS X</ui>
              </para>
            </TD>
            <TD>
              <para>
                <ui>Android</ui>
              </para>
            </TD>
            <TD>
              <para>
                <ui>Windows Phone 8.1</ui>
              </para>
            </TD>
            <TD>
              <para>
                <ui>Windows 8.1 and Windows RT 8.1</ui>
              </para>
            </TD><TD><para>
                <ui>Windows 10 Desktop and Mobile</ui>
              </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Cisco AnyConnect</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>No</para>
            </TD>
            <TD>
              <para>No</para>
            </TD><TD>
              <para>No</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Pulse Secure</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD><TD>
              <para>Yes</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>F5 Edge Client</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD><TD>
              <para>Yes</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Dell SonicWALL Mobile Connect</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD><TD>
              <para>Yes</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>CheckPoint Mobile VPN</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD>
            <TD>
              <para>Yes</para>
            </TD><TD>
              <para>Yes</para>
            </TD>
          </tr>
        </tbody>
      </table>
      <alert class="important">
        <para>Before you can use VPN profiles deployed to a device, you must install the applicable VPN app for the profile. You can use the information in the <link xlink:href="6da30550-9e8e-4333-b9b3-83928de3807a">Deploy apps to mobile devices in Microsoft Intune</link> topic to help you deploy the applicable app using <token>wit_nextref</token>.</para>
      </alert>
    </content>
  </section>
  <section>
    <title>How VPN profiles are secured</title>
    <content>
      <para>VPN profiles can use a number of different connection types and protocols from different manufacturers. These connections are typically secured using one of two methods:</para>
    </content>
    <sections>
      <section>
        <title>Certificates</title>
        <content>
          <para>When you create the VPN profile, you choose a SCEP <?xm-insertion_mark_start author="Nathan Bigman" time="20150812T131619+0200"?>or .PFX<?xm-insertion_mark_end?>certificate profile that you have previously created in <token>wit_nextref</token>. This is known as the identity certificate and is used to authenticate against a trusted certificate profile (or a root certificate) you created to establish that the user’s device is allowed to connect. The trusted certificate is deployed to the computer that authenticates the VPN connection, typically, the VPN server.</para>
          <para>For more information about how to create and use certificate profiles in <token>wit_nextref</token>, see <link xlink:href="8cbb8499-611d-4217-a7b4-e9b864785dd0">Use Microsoft Intune Certificate Profiles to secure access to company resources</link>.</para>
        </content>
      </section>
      <section>
        <title>Username and password</title>
        <content>
          <para>The user authenticates to the VPN server by providing their username and password.</para>
        </content>
      </section>
    </sections>
  </section>
  <section>
    <title>Create a VPN profile</title>
    <content>
      <para/>
      <procedure>
        <title/>
        <steps class="ordered">
          <step>
            <content>
              <para>In the <externalLink><linkText>Microsoft Intune administration console</linkText><linkUri>https://manage.microsoft.com</linkUri></externalLink>, click <ui>Policy</ui> &gt; <ui>Add Policy</ui>.</para>
            </content>
          </step>
          <step>
            <content>
              <para>Select a template for the new policy by expanding the relevant device type, then choose the VPN profile for that device:</para>
              <list class="bullet">
                <listItem>
                  <para>
                    <ui>VPN Profile (Android 4 and later)</ui>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <ui>VPN Profile (iOS 7.1 and later)</ui>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <ui>VPN Profile (Mac OS X 10.9 and later)</ui>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <ui>VPN Profile (Windows 8.1 and later)</ui>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <ui>VPN Profile (Windows Phone 8.1 and later)</ui>
                  </para>
                </listItem>
              <?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132037+0200"?><listItem>
                  <para>
                    <ui>VPN Profile (Windows 10 Desktop and Mobile and later)</ui>
                  </para>
                </listItem>
              <?xm-insertion_mark_end?></list>
              <para>You can only create and deploy a custom VPN profile policy. Recommended settings are not available.</para>
              <para>For more information about how to create and deploy policies, see the <link xlink:href="efb4dcd6-56ea-44a8-8fe2-6f1542fc75ec">Use policies to manage computers and mobile devices in Windows Intune</link> topic.</para>
            </content>
          </step>
          <step>
            <content>
              <para>
                <?Comment RS: Triple check this table! 2014-09-23T10:23:00Z  Id='2?>Use the following table to help you configure the VPN profile settings:<?CommentEnd Id='2'
    ?></para>
              <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
                <thead>
                  <tr>
                    <TD>
                      <para>Setting name</para>
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
                        <ui>Name</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Enter a unique name for the VPN profile to help you identify it in the <token>wit_nextref</token> console.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Description</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Provide a description that gives an overview of the VPN profile and other relevant information that helps you to locate it.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>VPN connection name (displayed to users)</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify a name for the VPN profile. This is the name that users will see in the list of available VPN connections on their devices.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Connection type</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Select one of the following connection types to use in the VPN profile:</para>
                     
                          <para>
                            <ui>Cisco AnyConnect</ui> (not available for Windows 8.1 or Windows Phone 8.1)</para>
                       
                          <para>
                            <ui>Pulse Secure</ui>
                          </para>
                       
                          <para>
                            <ui>F5 Edge Client</ui>
                          </para>
                       
                          <para>
                            <ui>Dell SonicWALL Mobile Connect</ui>
                          </para>
                       
                          <para>
                            <ui>CheckPoint Mobile VPN</ui>
                          </para>
                       
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>VPN server description</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify a description for the VPN server that devices will connect to.                     
                        <ui>Example:</ui> <userInputLocalizable>Contoso VPN Server</userInputLocalizable></para>
                     
                        <para>When the connection type is <ui>F5 Edge Client</ui>, use the <ui>Server list</ui> field to specify a list of server descriptions and IP addresses.</para>
                      
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Server IP address or FQDN</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.                         <ui>Examples:</ui> <userInput>192.168.1.1</userInput>, <userInput>vpn.contoso.com</userInput></para>
                     
                        <para>When the connection type is <ui>F5 Edge Client</ui>, use the <ui>Server list</ui> field to specify a list of server descriptions and IP addresses.</para>
                      
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Server list</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Click <ui>Add</ui> to add a new VPN server to use for the VPN connection. You can also specify which server is to be the default server for the connection.</para>
                      
                        <para>This option is displayed only when the connection type is <ui>F5 Edge Client</ui>.</para>
                     
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Send all network traffic through the VPN connection</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>If you select this option, all network traffic is sent through the VPN connection.</para>
                      <para>If you do not select this option, the client will dynamically negotiate the routes for split tunneling upon connecting to the 3rd party VPN server.</para>
                      <para>Only connections to the company network are sent over a VPN tunnel. VPN tunneling is not used when you connect to resources on the Internet.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Authentication method</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Select the authentication method used by the VPN connection:</para>
                     
                          <para>
                            <ui>Certificates</ui>
                          </para>
                       
                          <para>
                            <ui>Username and Password</ui> - this setting is not available when the connection type is <ui>Cisco AnyConnect</ui>.</para>
                        <para>The <ui>Authentication method</ui> option is not available for Windows 8.1
                          </para>
                       
                       
                      
                     
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Remember the user credentials at each logon</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Select this option to ensure that the user credentials are remembered so that the user does not have to enter credentials each time a connection is established.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Select a client certificate for client authentication (Identity Certificate)</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Select the client SCEP certificate that you previously created that will be used to authenticate the VPN connection. For more information about how to use certificate profiles in <token>wit_nextref</token>, see <link xlink:href="8cbb8499-611d-4217-a7b4-e9b864785dd0">Use Microsoft Intune Certificate Profiles to secure access to company resources</link>.</para>
                     
                        <para>This option is displayed only when the authentication method is <ui>Certificates</ui>.</para>
                    
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Role</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify the name of the user role that has access to this connection. A user role defines personal settings, options, and enables or disables certain access features.</para>
                     
                        <para>This option is displayed only when the connection type is <ui>Pulse Secure</ui>.</para>
                     
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Realm</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify the name of the authentication realm that you want to use. An authentication realm is a grouping of authentication resources that is used by the Pulse Secure connection type.</para>
                     
                        <para>This option is displayed only when the connection type is <ui>Pulse Secure</ui>.</para>
                    
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Login group or domain</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify the name of the login group or domain that you want to connect to.</para>
                     
                        <para>This option is displayed only when the connection type is <ui>Dell SonicWALL Mobile Connect</ui>.</para>
                    
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Fingerprint</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>Specify a string, for example "Contoso Fingerprint Code" that will be used to verify the VPN server can be trusted.</para>
                      <para>A fingerprint can be:</para>
                     
                          <para>Sent to the client so it knows to trust any server presenting that same fingerprint when connecting.</para>
                       
                          <para>If the device doesn’t already have the fingerprint it will prompt the user to trust the VPN server they are connecting to while showing the fingerprint (the user manually verifies the fingerprint and clicks <ui>trust</ui> to connect).</para>
                       
                        <para>This option is displayed only when the connection type is <ui>CheckPoint Mobile VPN</ui>.</para>
                    
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Per App VPN</ui> (iOS only)</para>
                    </TD>
                    <TD>
                      <para>Select this option if you want to associate this VPN connection with an iOS of Mac OS X app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see <link xlink:href="6da30550-9e8e-4333-b9b3-83928de3807a">Deploy software to mobile devices in Windows Intune</link>.</para>
                     
                        <para>
                          <?Comment RS: 144904 2014-10-15T09:13:00Z  Id='3?>If you deploy an app that is associated with a deployed VPN profile and then delete the VPN profile deployment, users will no longer be able to run the app.<?CommentEnd Id='3'
    ?></para>
                 
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Automatically detect proxy settings</ui> (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>If your VPN server requires a proxy server for the connection, specify whether you would like devices to automatically detect the connection settings.</para>
                      <para>For more information, see your Windows Server documentation.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Use automatic configuration script</ui> (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>If your VPN server requires a proxy server for the connection, specify whether you would like to use an automatic configuration script to define the settings and then specify a URL to the file containing the settings.</para>
                      <para>For more information, see your Windows Server documentation.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Use proxy server</ui> (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>If your VPN server requires a proxy server for the connection, select this option, then specify the address and port number of the proxy server.</para>
                      <para>For more information, see your Windows Server documentation.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Bypass proxy settings for local addresses</ui> (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only only)</para>
                    </TD>
                    <TD>
                      <para>If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</para>
                      <para>For more information, see your Windows Server documentation.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Custom XML</ui> (Windows 8.1<?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132139+0200"?> and later,<?xm-insertion_mark_end?> and Windows Phone 8.1<?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132146+0200"?> and later<?xm-insertion_mark_end?> only)</para>
                    </TD>
                    <TD>
                      <para>Allows you to specify custom XML commands that configure the VPN connection. Examples</para>
                   
                    
                          <para>For <ui>Pulse Secure</ui>:
                            <userInput>&lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;</userInput>
                          </para>
                      
                          <para>For <ui>CheckPoint Mobile VPN</ui>:
                            <userInput>&lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;</userInput>
                          </para>
                       
                          <para>For <ui>Dell SonicWALL Mobile Connect</ui>:
                            <userInput>&lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;</userInput>
                          </para>
                       
                          <para>For <ui>F5 Edge Client</ui>:
                            <userInput>&lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;</userInput>
                          </para>
                      
                      <para>Refer to each manufacturers VPN documentation for more information about how to write custom XML commands.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>DNS Suffix search list</ui> (Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>Specify one DNS suffix on each line. Each DNS suffix you specify will be searched when connecting to a website using a short name.</para>
                      <para>For example, specify the DNS suffices <ui>domain1.contoso.com</ui> and <ui>domain2.contoso.com</ui>, visit the URL <ui>http://mywebsite</ui>, and the URLs <ui>http://mywebsite.domain1.contoso.com</ui> and 
                         
                            <ui>http://mywebsite.domain2.contoso.com</ui> will be searched.
                          </para>
                       
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Bypass VPN when connected to company Wi-Fi network</ui> (Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>Specifies that the VPN connection will not be used when the device is connected to the company Wi-Fi network.</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>Bypass VPN when connected to home Wi-Fi network</ui> (Windows Phone 8.1 only)</para>
                    </TD>
                    <TD>
                      <para>Specifies that the VPN connection will not be used when the device is connected to a home Wi-Fi network.</para>
                    </TD>
                  </tr><tr><TD colspan="2"><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132536+0200"?><para><legacyBold>Corporate Boundaries settings for Windows 10 Desktop and Mobile</legacyBold></para><?xm-insertion_mark_end?></TD></tr><tr><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132249+0200"?><para>
                        Network traffic rules</para>
                    <?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T170726+0200"?><para>Set which protocols, local and remote port and address ranges will be enabled for the VPN connection.</para>
 <para>If you do not create a network traffic rule, all protocols, ports and address ranges are enabled. Once you create a rule, only the protocols, ports and address ranges that you specify in that rule or in additional rules will be used by the VPN connection.</para>
<?xm-insertion_mark_end?></TD></tr><tr><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132323+0200"?><para>Routes</para>
                    <?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T171048+0200"?><para>Which routes will use the VPN connection.</para><?xm-insertion_mark_end?></TD></tr><tr><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T132328+0200"?><para>DNS servers</para>
                    <?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="Nathan Bigman" time="20150812T150543+0200"?><para>Which DNS servers are used by the VPN connection once the connection has been established.</para><?xm-insertion_mark_end?></TD></tr>
                </tbody>
              </table>
            <?xm-insertion_mark_start author="Nathan Bigman" time="20150812T171446+0200"?><alert class="tip">
<para>Here's an example of when you might use corporate boundaries settings. If you want to enable VPN only for remote desktop, you would create a network traffic rule that allows traffic for protocol number 27 on external port 3996. No other traffic will use the VPN.</para><para>Defining routes in corporate boundaries is useful when your VPN connection type does not allow you to define how traffic is handled in split tunneling. In that case, use <ui>Routes</ui> to list the routes that will use the VPN.</para><para>You can restrict Windows 10 device VPN usage to specific apps by creating a custom OMA-URI setting. To learn more about customer URI settings see <link xlink:href="b05bbc3f-6256-490d-901f-3746203ca160">Custom URI settings for Windows 10 devices</link>.</para>
</alert><?xm-insertion_mark_end?></content>
          </step>
          <step>
            <content>
              <para>When you are finished, click <ui>Save Policy</ui>.</para>
            </content>
          </step>
        </steps>
        <conclusion>
          <content>
            <para>The new policy displays in the <ui>Configuration Policies</ui> node of the <ui>Policy</ui> workspace.</para>
          </content>
        </conclusion>
      </procedure>
    </content>
  </section>
  <section>
    <title>Deploy a VPN profile</title>
    <content>
      <procedure>
        <title/>
        <steps class="ordered">
          <step>
            <content>
              <para>Deploy the VPN profile to one or more groups of users or devices in your organization.</para>
            </content>
          </step>
        </steps>
        <conclusion>
          <content>
            <para>For more information about how to deploy policies, see <?xm-insertion_mark_start author="" time="20150615T215252+0200"?><link xlink:href="efb4dcd6-56ea-44a8-8fe2-6f1542fc75ec">Use policies to manage computers and mobile devices with Microsoft Intune</link><?xm-insertion_mark_end?><?xm-deletion_mark author="" time="20150615T215328+0200" data="&lt;maml:link xlink:href=&quot;3deb291f-4bef-49ba-bdc8-974426bab26d&quot; xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot; xmlns:xlink=&quot;http://www.w3.org/1999/xlink&quot;&gt;Use policies to manage computers and mobile devices in Microsoft Intune&lt;/maml:link&gt;"?>.</para>
            <para>A status summary and alerts on the <ui>Overview</ui> page of the <ui>Policy</ui> workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the <ui>Dashboard</ui> workspace.</para>
          </content>
        </conclusion>
      </procedure>
    </content>
  </section>
  <nextSteps>
    <content>
      <para>After successful deployment, users will see the VPN connection name you specified in the list of VPN connections on their device.</para>
    </content>
  </nextSteps>
  <relatedTopics>
    <link xlink:href="5b090c5a-6f12-4e60-ace0-c9929afaa9a3">Enable access to company resources using Windows Intune</link>
  </relatedTopics>
</developerWalkthroughDocument>

