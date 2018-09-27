# Manage User Access and Permissions<a name="manage-access"></a>

Access to features within Amazon Chime is determined by the permissions tier assigned to the user\. The ability to sign into Amazon Chime is managed by suspending or activating users\. 

As an Amazon Chime administrator, you can manage the permissions tiers of users in your account\. However, the ability to suspend a user account is only available to enterprise team administrators\. Administrators of team accounts can remove users from their accounts so that they are no longer paying for the user’s permissions\. However, they can't suspend the user and prevent them from signing in\. 

## Manage Permissions<a name="manage-licenses"></a>

How permissions are managed is determined by whether Active Directory or Okta is configured\. If you have Active Directory or Okta configured for your account, permissions management is handled through group memberships\. If Active Directory or Okta is not configured, permissions are managed through the Amazon Chime console\. 

### Team Accounts and Enterprise Login with Amazon<a name="manage-team-licenses"></a>

For administrators of team and enterprise LWA accounts, where users sign in with their Login with Amazon \(LwA\) accounts, licenses are managed from either the **Users** or **User details** pages\. 

**To manage Amazon Chime licenses for team accounts and enterprise LWA**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Amazon Chime account\.

1. In the navigation pane, choose **Users**\.

1. Select the check boxes for the users and then choose **User actions**, **Assign permissions**, **Pro** or **Basic**, and **Assign**\.

### Enterprise Active Directory or Enterprise OpenID Connect Accounts<a name="manage-AD-licenses"></a>

The permissions tier for users who sign in with their Active Directory or Okta credentials is determined by directory memberships\. If they are a member of an Active Directory or Okta group that has been assigned Pro, they are Pro\. If they are a member of an Active Directory or Okta group that has been assigned Basic, they are Basic\. Users without Pro or Basic permissions can't sign into Amazon Chime\.

## Invite and Remove Users<a name="invite-users-team"></a>

Use the following information to invite and remove users from your Amazon Chime account\.

### Team Accounts<a name="invite-team"></a>

With a team account, you can use the Amazon Chime console to invite users from any email domain\.

**Note**  
A user's 30\-day trial ends when they accept the invitation\.

**To invite users to a team account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the team account\.

1. On the **Users** page, choose **Invite users**\.

1. Type the email addresses of the users to invite \(separate multiple email addresses with a semicolon **;**\) and choose **Invite users**\.

Use the following procedure to remove users from a team account\. This disassociates the user from the account and removes any permissions that you purchased for them\. The user can still access Amazon Chime, but is no longer a paid member of your Amazon Chime account\. The user can no longer use autocomplete in **Contacts** to find new team users\.

**To remove users from a team account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the team account\.

1. On the **Users** page, select the users to remove and choose **User actions**, **Remove user**\.

### Enterprise Accounts<a name="invite-enterprise"></a>

With an enterprise account, any users that register for Amazon Chime with an email address for your claimed domains are automatically added to your account\. If you configured Active Directory or Okta, the user must not only have an email address that uses one of your claimed domains, but they must also be members of the directory you configured for Amazon Chime\.

**To invite users to an enterprise account**

1. Send an invitation email to the users in your organization and instruct them to follow the steps in [Create an Amazon Chime Account](https://docs.aws.amazon.com/chime/latest/ug/chime-create-account.html) in the *Amazon Chime User Guide*\.

1. Users use an email address with the one of the domains that you claimed for your account\.

After your users complete the steps to create their Amazon Chime accounts, they automatically appear on the **Users** page for the enterprise account\.

Use the following procedure to suspend users from an enterprise account\. This prevents users from logging in to Amazon Chime\.

**To suspend users from an enterprise account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the enterprise account\.

1. On the **Users** page, select the users to remove and choose **User actions**, **Suspend user**\.

**To suspend users from an enterprise Active Directory or OpenID Connect \(Okta\) account**
+ Choose one of the following options:
  + Suspend or mark the user inactive the  from your Active Directory or Okta Administrator Dashboard\.
  + Make sure that the user is not in an Active Directory group that has Basic or Pro permissions\.