# Managing user access and permissions<a name="manage-access"></a>

Access to features within Amazon Chime is determined by the permissions tier assigned to the user\. The ability to sign into Amazon Chime is managed by suspending or activating users\. 

As an Amazon Chime administrator, you can manage the permissions tiers of users in your account\. However, the ability to suspend a user account is only available to Enterprise account administrators\. Administrators of Team accounts can remove users from their accounts so that they are no longer paying for the user’s permissions\. However, they can't suspend the user and prevent them from signing in\. 

## Managing permissions<a name="manage-licenses"></a>

How permissions are managed is determined by whether Active Directory or Okta is configured\. If you have Active Directory or Okta configured for your account, permissions management is handled through group memberships\. If Active Directory or Okta is not configured, permissions are managed through the Amazon Chime console\. 

### Team accounts and Enterprise Login with Amazon<a name="manage-team-licenses"></a>

For administrators of Team and Enterprise LWA accounts, where users sign in with their Login with Amazon \(LwA\) accounts, licenses are managed from either the **Users** or **User details** pages\. 

**To manage Amazon Chime licenses for Team accounts and Enterprise LWA**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Amazon Chime account\.

1. In the navigation pane, choose **Users**\.

1. Select the check boxes for the users and then choose **Actions**, **Assign permissions**, **Pro** or **Basic**, and **Assign**\.

### Enterprise Active Directory or Enterprise OpenID Connect accounts<a name="manage-AD-licenses"></a>

The permissions tier for users who sign in with their Active Directory or Okta credentials is determined by directory memberships\. If they are a member of an Active Directory or Okta group that has been assigned Pro, they are Pro\. If they are a member of an Active Directory or Okta group that has been assigned Basic, they are Basic\. Users without Pro or Basic permissions can't sign into Amazon Chime\.

## Inviting and suspending users<a name="invite-users-team"></a>

Use the following information to invite or suspend users from your Amazon Chime account\. The procedures are different for Team accounts and Enterprise accounts\.

### Team accounts<a name="invite-team"></a>

With a Team account, you can use the Amazon Chime console to invite users from any email domain\.

**Note**  
A user's 30\-day trial ends when they accept the invitation\.

**To invite users to a Team account**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Team account\.

1. On the **Users** page, choose **Invite users**\.

1. Type the email addresses of the users to invite \(separate multiple email addresses with a semicolon **;**\) and choose **Invite users**\.

Use the following procedure to remove users from a Team account\. This disassociates the user from the account and removes any permissions that you purchased for them\. The user can still access Amazon Chime, but is no longer a paid member of your Amazon Chime account\. The user can no longer use autocomplete in **Contacts** to find new Team users\.

**To remove users from a Team account**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Team account\.

1. On the **Users** page, select the users to remove and choose **Actions**, **Remove user**\.

### Enterprise accounts<a name="invite-enterprise"></a>

With an Enterprise account, any users that register for Amazon Chime with an email address for your claimed domains are automatically added to your account\. If you configured Active Directory or Okta, the user must not only have an email address that uses one of your claimed domains, but they must also be members of the directory you configured for Amazon Chime\.

**To invite users to an Enterprise account**
+ Send an invitation email to the users in your organization and instruct them to follow the steps in [Create an Amazon Chime account](https://docs.aws.amazon.com/chime/latest/ug/chime-create-account.html) in the *Amazon Chime User Guide*\.

Users use an email address with the one of the domains that you claimed for your account\. After your users complete the steps to create their Amazon Chime accounts, they automatically appear on the **Users** page for the Enterprise account\.

Use the following procedure to suspend users from an Enterprise account\. This prevents users from logging in to Amazon Chime\.

**To suspend users from an Enterprise account**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. On the **Accounts** page, select the name of the Enterprise account\.

1. On the **Users** page, select the users to suspend and choose **Actions**, **Suspend user**\.

1. Select the check box, and choose **Suspend**\.

**To suspend users from an Enterprise Active Directory or OpenID Connect \(Okta\) account**
+ Choose one of the following options:
  + Suspend or mark the user inactive from your Active Directory or Okta Administrator Dashboard\.
  + Make sure that the user is not in an Active Directory group that has Basic or Pro permissions\.