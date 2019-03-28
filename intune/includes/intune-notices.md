
These notices provide important information that can help you prepare for future Intune changes and features. 

### Change in enrollment workflow with Intune Company Portal on corporate iOS devices authenticating with Setup Assistant <!-- 1927359 -->
There's an upcoming change in workflow for enrollment of iOS devices through one of Apple’s corporate device enrollment methods - Apple Configurator, Apple Business Manager, Apple School Manager, or the Apple Device Enrollment Program (DEP), when using Setup Assistant for authentication. This change applies only to devices enrolled with user affinity.

#### How does this affect me?
When this change is rolled out in ~~March~~ April, enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. There will be an improved workflow to enroll iOS devices through the methods listed above. Note:

- When enrolling new devices and authenticating with Setup Assistant, you’ll be able to choose whether or not to deploy the Company Portal app automatically. End users will no longer see the “Identify your device” screen and the “Confirm your device” screen in the enrollment flow.  
- On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, you must take action if you want to enable Conditional Access. You’ll have to configure an app configuration policy with a specific xml to push the Company Portal down to these devices. Directions to do this are in the blog post at the Additional Information link. If you choose to push the Company Portal in this manner, end users will no longer see the “Identify your device” screen and the “Confirm your device” screen in the enrollment flow. 
- After this change is rolled out, if you haven't deployed the Company Portal with the app configuration profile mentioned above and if end users download the Company Portal app from the App store, they'll can sign in, but they'll get an error message. They won't be able to use the app for Conditional Access. 

#### What do I need to do to prepare for this change?
If you plan on using the modified workflow, you'll want to update your end user guidance to indicate that:

- End users will no longer see the two screens mentioned above in the enrollment flow. 
- They'll need to sign in to the Company Portal when it's automatically deployed and not download it from the app store. 

You can choose to create an app configuration policy now if needed, in preparation for this change. When this new workflow rolls out, you’ll see updated enrollment profiles in the console. We’ll also inform you of this rollout through the Message Center. After this, you’ll need to take the action so your end users can enroll through DEP by authenticating with Setup Assistant and you can use Company Portal for Conditional Access.

See our support blog post at the Additional Information link for more details about this change.

#### Additional Information 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### Plan for Change: User experience update to Intune Company Portal app for iOS
We’re excited to share that Intune will soon be releasing a major user experience update to the iOS Company Portal app. The update will feature a visual redesign of the home page with advanced filters and faster access to apps and books.

#### How does this affect me?
This user experience update, while maintaining current iOS Company Portal functionality, will feature:
- A home page with native iOS look and feel 
- Filtering capabilities on content lists and search, including the ability to filter by content type (apps or ebooks) and availability (device management required or available without enrollment)
- Ability to search ebooks
- Search history for apps and ebooks

If you’re part of the Apple TestFlight program, you will be notified about the pre-release version of Intune’s updated iOS Company Portal app when it becomes available. If you’re not part of the Apple TestFlight program, it’s not too late to register. Registering will enable you to use the updated Company Portal app before it’s available to your end users. You'll can also provide feedback directly to the Intune team.  

#### What can I do to prepare for this change?
You don't need to take any action; these changes will be released in an upcoming iOS CP app release. 

#### Additional Information
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

### Check your “Delay Visibility of Software updates” setting in Intune 

We shared in MC171466 that we were moving a few settings around in the console. With the March update to Intune, we'll completely remove the “Delay Visibility of Software updates” setting from the iOS update policy blade. This will not change the way your scheduled software updates apply but it may affect how long the visibility of an update is delayed for end users. You may need to take action before the end of March if you use this setting. 

#### How does this affect me?
After the February Intune service update, you’ll notice that the setting appears both in Device restriction profiles in the console and in iOS update policies in the Software update blade. When you see this change reflected in the console, here’s what you may need to do.

- For existing Update policies for iOS: If you have custom configured this setting to anything other than the default 30 days, and want your existing configurations for the Delay visibility setting to continue to apply after the end of March, you’ll have to create a new iOS device restriction profile. Here, the Delay visibility setting will need to have the same values as in the existing iOS update policy and be targeted to the same groups. After the March service update, you will no longer be able to edit values for this setting in existing iOS update policies since it will no longer be visible in this blade. You will configure this setting in the new profiles instead.
  If the value for number of days you can delay visibility does not match in both locations for custom configured setting values, the Delay Visibility setting will not work, and end users will see the update on their devices as soon as it is available. This may have minimal impact for most customers since the other settings in the Software Update Policy blade have always taken precedence over this setting in the console.
- For new update policies for iOS: If you try to create new policies in the Software updates blade after the Intune February service update, you will see this setting grayed out. You’ll see a note in the console redirecting you to the Device configuration blade if you wish to delay visibility of updates.

#### What can I do to prepare for this change?
You do not need to take action if you do not use this setting or do not want to delay visibility of software updates for your end users.

If you wish to delay visibility of updates, start configuring the setting in new profiles in the Device Configuration blade under Device Restrictions > General. If you have this setting custom configured in existing iOS update policies, create a new equivalent device restriction profile with the same value for “days” to delay visibility of updates to your users, after the February update and before the March update rolls out. 

You may want to update your IT Pro guidance and inform your helpdesk.

See our support blog post at Additional Information for details on how to configure this setting.

#### Additional Information 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)

### Plan for change: Upcoming fix for Windows 10 email profiles in Intune <!--3904031-->
We're updating the way Intune writes email profiles for Windows 10 in the April update to the Intune service to fix a bug as well as to ensure your email profiles continue to work in future versions of Windows 10. There is action you need to take after this fix is deployed.

#### How does this affect me?
This change impacts you if you use Windows 10 email profiles with
- The nativeMail client on Windows 10 desktops OR
- The Outlookemail client on Windows 10 Mobile

This impacts both Intune standalone and hybrid Mobile Device Management (MDM) customers.

After the April update rolls out, you’ll need to re-create these profiles in the Intune console (in the Configuration Manager admin console if you’re using hybrid MDM).

If you do not take action, here’s what you’ll see for profiles created before the April update:

- Existing e-mail profiles will show up in error state in the Intune console or Configuration Manager admin console, but end users will still have access to email. However, after a subsequent Windows update rolls out, these profiles will not work. End users on devices targeted with these profiles will lose access to email.
- Edits made to these profiles after April will not be reflected in targeted devices.
- Selective wipe will not work for removing these profiles even after the fix is rolled out in April.

If you take action and re-create email profiles, end users will have to go through steps similar to those when an email profile is deployed for the first time. Their email will be blocked from syncing until they accept the update that applies the new profile.

#### What do I need to do to prepare for this change?
You need to take action only after the fix is rolled out with the April update. We’ll reach out to you through the Message Center when this change goes live so you can start to re-create your profiles in Intune.

If you use Windows 10 email profiles in Intune, you will need to take the following steps:

1. Capture existing Win 10 profile settings
2. Unassign and/or delete existing profiles
3. Create new profiles using the captured settings and assign the new profiles to the same groups

You may need to notify your end users and let your helpdesk know of this change. Please refer to the support blog post at Additional Information for error details and instructions for re-creating these profiles.

#### Additional Information
https://aka.ms/Win10EmailProfiles