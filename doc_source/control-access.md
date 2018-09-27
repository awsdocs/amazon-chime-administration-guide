# Control Access to the Amazon Chime Console<a name="control-access"></a>

As an administrator, you must complete the following tasks to allow users in your account to access the Amazon Chime console\.

## Create an IAM User<a name="iam-user"></a>

Services in AWS, such as Amazon Chime, require that you provide credentials when you access them\. This allows the service to determine whether you have permissions to access its resources\. We recommend that you avoid accessing AWS with your AWS account root credentials\. Instead, use AWS Identity and Access Management \(IAM\)\. Create one or more IAM users, add the users to an IAM group, and grant permissions to the group by attaching IAM policies\. All of the users in that group inherit the permissions\. Your IAM users can then access the AWS and Amazon Chime consoles using their account ID, IAM user name, and password\.

For more information about setting up an IAM user, see [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html)\. For information about IAM, see [What is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) 

## Attach Required IAM User Policies<a name="iam-policies"></a>

By default, IAM users don't have permission to access the Amazon Chime console\. To provide access, you must create IAM policies that grant IAM users permission to use the specific resources and actions they'll need\. You must then attach those policies to IAM users or groups that require those permissions\.

When you attach a policy to a user or group, it allows or denies the users permission to perform the specified tasks on the specified resources\. 

To make creating policies easier, Amazon Chime supports using the following AWS managed policies\. AWS managed policies are built for specific use cases and are automatically updated by the Amazon Chime service team when new capabilities are added\. When you use these policies, your users have immediate access to the Amazon Chime console without the need to create or maintain your own policies\.


| AWS Managed Policies for Amazon Chime | Description | 
| --- | --- | 
| AmazonChimeFullAccess \(FA\) |  Full access for Amazon Chime administrators who configure and manage the service  | 
|  AmazonChimeReadOnly \(RO\)  |  Read\-only access to the console  | 
|  AmazonChimeUserManagement \(UM\)  |  Full user management capabilities and read\-only access to account settings and configuration  | 

To create your own policies, review the [Amazon Chime Actions](#available-actions) below for a list of all of the actions that you can allow or deny in your policy\. For more information about managing and creating IAM policies, see [Managing IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage.html)\. For information about how to attach managed policies to an IAM user, see [Attaching and Detaching IAM Policies ](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html)\.

## **Read\-Only Policy Example**<a name="read-only-access"></a>

This example policy provides read\-only access to the Amazon Chime console\. You can use this as a base for any customizations you choose to make\. 

**Note**  
If you create a custom policy instead of using an AWS managed policy, when Amazon Chime adds new actions, it does not automatically update your policy\. Instead, you must review the changes and manually update your policy\.

```
{
  "Version": "2012-10-17",  
  "Statement": [
    {
      "Action": [
          "chime:ListAccounts",
          "chime:GetAccount",
          "chime:GetAccountSettings",
          "chime:ListUsers",
          "chime:GetUser",
          "chime:GetUserByEmail",
          "chime:ListAccountUsageReportData",
          "chime:ListDomains",
          "chime:GetDomain",
          "chime:ListGroups"
          "chime:ListDirectories",           
          "chime:GetAccountResource"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
```

## Amazon Chime Actions<a name="available-actions"></a>

The following is the complete list of Amazon Chime actions that are available if you create a custom IAM policy for your console users\. For more information about creating custom policies, see [Creating IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html)\. For more information about the managed policies for Amazon Chime, see[Attach Required IAM User Policies](#iam-policies)\.

**Note**  
The following abbreviations are used in the table:  
FA: FullAccess
UM: UserManagement
RO: ReadOnly


| Action | Description | Managed Policy for Amazon Chime | 
| --- | --- | --- | 
|  Accounts  |  |  | 
|  `chime:CreateAccount`  |  Creates a new Amazon Chime account\.  | FA | 
|  `chime:RenameAccount`  |  Modifies the account name for your Amazon Chime enterprise or team account\.  | FA | 
|  `chime:GetAccountSettings`  |  Shows your Amazon Chime account settings\.  | FA, UM, RO | 
|  `chime:UpdateAccountSettings`  | Modifies your Amazon Chime account settings\. | FA, UM | 
|  `chime:ListAccounts`  |  Lists the Amazon Chime accounts associated with your AWS account\.  | FA, UM, RO | 
|  `chime:GetAccount`  |  Gets the account details for an Amazon Chime account\.  | FA, UM, RO | 
|  `chime:DeleteAccount`  |  Deletes an Amazon Chime account\.  | FA | 
| Users |  |  | 
|  `chime:ListUsers`  |  Lists the users in an Amazon Chime account\.  | FA, UM, RO | 
|  `chime:GetUser`  |  Gets the user details for an Amazon Chime user\.  | FA, UM, RO | 
|  `chime:GetUserByEmail`  | Gets the user details for an Amazon Chime user based on the email address in an Amazon Chime enterprise or team account\. | FA, UM, RO | 
|  `chime:InviteUsers`  |  Invites new users to an Amazon Chime account\.  | FA, UM | 
|  `chime:SuspendUsers`  |  Suspend users from an Amazon Chime enterprise account\.  | FA, UM | 
|  `chime:ActivateUsers`  |  Activates users in an Amazon Chime enterprise account\.  | FA, UM | 
|  `chime:UpdateUserLicenses`  |  Manages the licenses for your Amazon Chime users\.  | FA, UM | 
|  `chime:ResetPersonalPin`  |  Resets the personal meeting PIN for an Amazon Chime user\.  | FA, UM | 
| chime:LogoutUser | Signs a user out of all their devices\. | FA, UM | 
| Reports |  |  | 
| chime:ListAccountUsageReportData | Lists Amazon Chime account usage reporting data\. | FA, UM, RO | 
| chime:GetUserActivityReportData | Shows a summary of user activity on the User details page\. | FA, UM, RO | 
| chime:GetMeetingDetail | Shows attendee, connection, and other details for a meeting\. | FA, UM | 
| chime:ListMeetingEvents | Lists all events that occurred for a meeting\. | FA, UM | 
| chime:ListMeetingReportData | Lists meetings that ended during the date range\. | FA, UM | 
|  |  |  | 
|  |  |  | 
|  |  |  | 
| Domains |  |  | 
|  `chime:ListDomains`  |  Lists domains associated with your Amazon Chime account\.  | FA, UM, RO | 
|  `chime:AddDomain`  |  Adds a domain to your Amazon Chime account\.  | FA | 
|  `chime:GetDomain`  |  Shows domain details for a domain associated with your Amazon Chime account\.  | FA, UM, RO | 
|  `chime:DeleteDomain`  |  Deletes a domain from your Amazon Chime account\.  | FA | 
| Active Directory |  |  | 
| chime:AuthorizeDirectory | Authorizes an Active Directory to associate with your Amazon Chime enterprise account\. | FA | 
| chime:UnauthorizeDirectory | Unauthorizes an Active Directory from your Amazon Chime enterprise account\. | FA | 
| chime:ListDirectories | Lists active Microsoft Active Directories hosted in the Directory Service of your AWS account\. | FA, UM, RO | 
| chime:ConnectDirectory | Connects an Active Directory to your Amazon Chime enterprise account\. | FA | 
| chime:DisconnectDirectory | Disconnects the Active Directory from your Amazon Chime enterprise account\. | FA | 
|  |  |  | 
|  |  |  | 
|  |  |  | 
| Okta |  |  | 
| chime:ListApiKeys | Lists the SCIM access keys defined for your Amazon Chime account and Okta configuration\. | FA | 
| chime:CreateApiKey | Generates a new SCIM access key for your Amazon Chime account and Okta configuration\. | FA | 
| chime:DeleteApiKey | Deletes the specified SCIM access key associated with your Amazon Chime account and Okta configuration\. | FA | 
| chime:GetAccountWithOpenIdConfig | Gets the account details and OpenIdConfig attributes for your Amazon Chime account\. | FA | 
| chime:UpdateAccountOpenIdConfig | Updates the OpenIdConfig attributes for your Amazon Chime account\. | FA | 
| chime:DeleteAccountOpenIdConfig | Deletes the OpenIdConfig attributes from your Amazon Chime account, | FA | 
| Directory Groups |  |  | 
| chime:ListGroups | Lists Active Directory user groups associated with your Amazon Chime enterprise account\. | FA, UM, RO | 
| chime:AddOrUpdateGroups | Adds new or updated existing Active Directory user groups associated with your Amazon Chime enterprise account\. | FA | 
| chime:DeleteGroups | Deletes Active Directory user groups from your Amazon Chime enterprise account\. | FA | 
| Amazon Chime Support |  |  | 
| chime:SubmitSupportRequest | Submits a support ticket from the Amazon Chime console\. | FA, UM | 
| AWS Account Delegation |  |  | 
| chime:AcceptDelegate | Accepts requests to share management of an Amazon Chime account with another AWS account\. | FA | 
| chime:ValidateDelegate | Allows process to share the AWS account name and Amazon Chime account name\. | FA | 
| chime:ListDelegates | Displays shared account management status on the Account Summary page\. | FA, UM, RO | 
| chime:DeleteDelegate | Removes the shared AWS account management\. | FA | 