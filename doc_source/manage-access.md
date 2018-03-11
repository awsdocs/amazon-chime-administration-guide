# Manage User Access and Licenses<a name="manage-access"></a>

Access to features within Amazon Chime is determined by the license type assigned to the user\. The ability to sign into Amazon Chime is managed by suspending or activating users\. As an Amazon Chime administrator, you can manage license types of users in your account, but the ability to suspend a user account is only available to enterprise team administrators\. Administrators of team accounts can remove users from their accounts so they are no longer paying for the user’s license, but they can't suspend the user and prevent them from signing in\. 

## Manage Licenses<a name="manage-licenses"></a>

How license types are managed is determined by whether you have Active Directory configured\. If you have Active Directory configured for your account, license management is handled through group memberships\. If Active Directory is not configured, license types are managed through the Amazon Chime console\. 

### Team Accounts and Enterprise Login with Amazon<a name="manage-team-licenses"></a>

For administrators of team and enterprise LWA accounts, where users sign in with their Login with Amazon \(LwA\) accounts, licenses are managed from either the **Users** or **User details** pages\. 

**To manage Amazon Chime licenses for team accounts and enterprise LWA**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Amazon Chime account\.

1. In the navigation pane, choose **Users**\.

1. Select the check boxes for the users and then choose **User actions**, **Assign user license**, **Pro** or **Plus**, and **Assign**\.

### Enterprise Active Directory Accounts<a name="manage-AD-licenses"></a>

The license type for users that sign in with their Active Directory credentials is determined by group memberships\. If they are a member of an Active Directory group that has been assigned Pro, they are Pro\. If they are a member of a group that has been assigned Plus, then they have Plus status\. Users not in any of the groups with Pro or Plus license tiers can't sign into Amazon Chime\.

## Invite and Remove Users<a name="invite-users-team"></a>

### Team Accounts<a name="invite-team"></a>

After you create an Amazon Chime team account, you can invite\. With a team account, you can use the Amazon Chime console to invite users from any email domain\.

**To invite users to a team account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the team account\.

1. On the **Users** page, choose **Invite users**\.

1. Type the email addresses of the users to invite \(separate multiple email addresses with a semicolon **;**\) and then choose **Invite users**\.

Use the following procedure to remove users from a team account\. This disassociates the user from the account and removes any license that you purchased for them\. The user can still access Amazon Chime, but is no longer a paid member of your Amazon Chime account\. The user can no longer use autocomplete in **Contacts** to find new team users\.

**To remove users from a team account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the team account\.

1. On the **Users** page, select the users to remove and choose **User actions**, **Remove user**\.

### Enterprise Accounts<a name="invite-enterprise"></a>

With an enterprise account, any users that register for Amazon Chime with an email address for your claimed domains are automatically added to your account\. If you configured Active Directory, the user must not only have an email address that uses one of your claimed domains, but they must also be members of the group you configured for Amazon Chime\.

**To invite users to an enterprise account**

1. Send an invitation email to the users in your organization and instruct them to follow the steps in [Create an Amazon Chime Account](http://docs.aws.amazon.com/chime/latest/ug/chime-create-account.html) in the *Amazon Chime User Guide*\.

1. Users use an email address with the one of the domains that you claimed for your account\.

1. After your users complete the steps to create their Amazon Chime accounts, they automatically appear on the **Users** page for the enterprise account\.

Use the following procedure to suspend users from an enterprise account\. This prevents them users from logging in to Amazon Chime\.

**To suspend users from an enterprise account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the enterprise account\.

1. On the **Users** page, select the users to remove and choose **User actions**, **Suspend user**\.