# Controlling Access to the Amazon Chime Console<a name="control-access"></a>

If you want to provide other users with administrator permissions, while controlling their access to the Amazon Chime console for your account, complete the tasks in the following sections\.

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

For more information, see [Controlling Access to Amazon Chime admin console using IAM](https://answers.chime.aws/articles/317/amazon-chime-actions-for-iam-policies.html)\.

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

The following is the complete list of Amazon Chime actions that are available if you create a custom IAM policy for your console users\. For more information about creating custom policies, see [Creating IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html)\. For more information about the managed policies for Amazon Chime, see [Attach Required IAM User Policies](#iam-policies)\.

**Note**  
The following abbreviations are used in the table:  
FA: FullAccess
UM: UserManagement
RO: ReadOnly


| Action | Description | Managed Policy | 
| --- | --- | --- | 
| **Accounts** | 
|  `chime:CreateAccount`  |  Grants permission to create an Amazon Chime account under the administrator's AWS account\.  | FA | 
|  `chime:DeleteAccount`  |  Grants permission to delete the specified Amazon Chime account\.  | FA | 
|  `chime:GetAccount`  |  Grants permission to get details for the specified Amazon Chime account\.  | FA, UM, RO | 
|  `chime:ListAccounts`  |  Grants permission to list the Amazon Chime accounts under the administrator's AWS account\.  | FA, UM, RO | 
|  `chime:RenameAccount`  |  Grants permission to modify the account name for the Amazon Chime Enterprise or Team account\.  | FA | 
| **Users** | 
|  `chime:ActivateUsers`  |  Grants permission to activate users in an Amazon Chime Enterprise account\.  | FA, UM | 
| `chime:BatchSuspendUser` | Grants permission to suspend up to 50 users from a Team or EnterpriseLWA Amazon Chime account\. | FA, UM | 
| `chime:BatchUnsuspendUser` | Grants permission to remove the suspension from up to 50 previously suspended users for the specified Amazon Chime EnterpriseLWA account\. | FA, UM | 
| `chime:BatchUpdateUser` | Grants permission to update user details within the UpdateUserRequestItem object for up to 20 users for the specified Amazon Chime account\. | FA, UM | 
|  `chime:GetAccountSettings`  |  Grants permission to get account settings for the specified Amazon Chime account ID\.  | FA, UM, RO | 
|  `chime:GetUser`  |  Grants permission to get details for the specified user ID\.  | FA, UM, RO | 
|  `chime:GetUserByEmail`  | Grants permission to get user details for an Amazon Chime user based on the email address in an Amazon Chime Enterprise or Team account\. | FA, UM, RO | 
|  `chime:InviteUsers`  |  Grants permission to invite as many as 50 users to the specified Amazon Chime account\.  | FA, UM | 
|  `chime:ListUsers`  |  Grants permission to list the users that belong to the specified Amazon Chime account\.  | FA, UM, RO | 
| `chime:LogoutUser` | Grants permission to log out the specified user from all of the devices they are currently logged in to\. | FA, UM | 
|  `chime:ResetPersonalPin`  |  Grants permission to reset the personal meeting PIN for the specified user on an Amazon Chime account\.  | FA, UM | 
|  `chime:SuspendUsers`  |  Grants permission to suspend users from an Amazon Chime Enterprise account\.  | FA, UM | 
|  `chime:UpdateAccountSettings`  | Grants permission to update the settings for the specified Amazon Chime account\. | FA, UM | 
|  `chime:UpdateUserLicenses`  |  Grants permission to update the licenses for your Amazon Chime users\.  | FA, UM | 
| **Reporting** | 
| `chime:GetMeetingDetail` | Grants permission to get attendee, connection, and other details for a meeting\. | FA, UM | 
| chime:GetUserActivityReportData | Grants permission to get a summary of user activity on the User details page\. | FA, UM, RO | 
| `chime:ListAccountUsageReportData` | Grants permission to list Amazon Chime account usage reporting data\. | FA, UM, RO | 
| `chime:ListMeetingEvents` | Grants permission to list all events that occurred for a specified meeting\. | FA, UM | 
| `chime:ListMeetingReportData` | Grants permission to list meetings that ended during the specified date range\. | FA, UM | 
| **Attachments** | 
| `chime:RetrieveDataExport` | Grants permission to download the file containing links to all user attachments returned as part of the `Request attachments` action\. | FA | 
| `chime:StartDataExport` | Grants permission to submit the `Request attachments` request\. | FA | 
| **Domains** | 
|  `chime:AddDomain`  |  Grants permission to add a domain to your Amazon Chime account\.  | FA | 
|  `chime:DeleteDomain`  |  Grants permission to delete a domain from your Amazon Chime account\.  | FA | 
|  `chime:GetDomain`  |  Grants permission to get domain details for a domain associated with your Amazon Chime account\.  | FA, UM, RO | 
|  `chime:ListDomains`  |  Grants permission to list domains associated with your Amazon Chime account\.  | FA, UM, RO | 
| **Active Directory** | 
| `chime:AddOrUpdateGroups` | Grants permission to add new or update existing Active Directory or Okta user groups associated with your Amazon Chime Enterprise account\. | FA | 
| `chime:AuthorizeDirectory` | Grants permission to authorize an Active Directory for your Amazon Chime Enterprise account\. | FA | 
| `chime:ConnectDirectory` | Grants permission to connect an Active Directory to your Amazon Chime Enterprise account\. | FA | 
| `chime:DeleteGroups` | Grants permission to delete Active Directory or Okta user groups from your Amazon Chime Enterprise account\. | FA | 
| `chime:DisconnectDirectory` | Grants permission to disconnect the Active Directory from your Amazon Chime Enterprise account\. | FA | 
| `chime:ListDirectories` | Grants permission to list active Active Directories hosted in the Directory Service of your AWS account\. | FA, UM, RO | 
| `chime:ListGroups` | Grants permission to list Active Directory or Okta user groups associated with your Amazon Chime Enterprise account\. | FA, UM, RO | 
| `chime:UnauthorizeDirectory` | Grants permission to unauthorize an Active Directory from your Amazon Chime Enterprise account\. | FA | 
| **Okta** | 
| `chime:CreateApiKey` | Grants permission to create a new SCIM access key for your Amazon Chime account and Okta configuration\. | FA | 
| `chime:DeleteAccountOpenIdConfig` | Grants permission to delete the `OpenIdConfig` attributes from your Amazon Chime account\. | FA | 
| `chime:DeleteApiKey` | Grants permission to delete the specified SCIM access key associated with your Amazon Chime account and Okta configuration\. | FA | 
| `chime:GetAccountWithOpenIdConfig` | Grants permission to get the account details and `OpenIdConfig` attributes for your Amazon Chime account\. | FA | 
| `chime:ListApiKeys` | Grants permission to list the SCIM access keys defined for your Amazon Chime account and Okta configuration\. | FA | 
| `chime:UpdateAccountOpenIdConfig` | Grants permission to update the `OpenIdConfig` attributes for your Amazon Chime account\. | FA | 
| **Calling** | 
| `chime:AssociatePhoneNumberWithUser` | Grants permission to associate a phone number with an Amazon Chime user\. | FA, UM | 
| `chime:AssociatePhoneNumbersWithVoiceConnector` | Grants permission to associate phone numbers with an Amazon Chime Voice Connector\. | FA | 
| `chime:BatchDeletePhoneNumber` | Grants permission to move up to 50 phone numbers to the deletion queue\. | FA | 
| `chime:BatchUpdatePhoneNumber` | Grants permission to update phone number details within the UpdatePhoneNumberRequestItem object for up to 50 phone numbers\. | FA | 
| `chime:CreatePhoneNumberOrder` | Grants permission to create a phone number order with the carriers\. | FA | 
| `chime:CreateVoiceConnector` | Grants permission to create an Amazon Chime Voice Connector under the administrator's AWS account\. | FA | 
| `chime:DeletePhoneNumber` | Grants permission to move a phone number to the deletion queue\. | FA | 
| `chime:DeleteVoiceConnector` | Grants permission to delete the specified Amazon Chime Voice Connector\. | FA | 
| `chime:DeleteVoiceConnectorOrigination` | Grants permission to delete the origination settings for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:DeleteVoiceConnectorTermination` | Grants permission to delete the termination settings for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:DeleteVoiceConnectorTerminationCredentials` | Grants permission to delete SIP termination credentials for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:DisassociatePhoneNumberFromUser` | Grants permission to disassociate the primary provisioned phone number from the specified Amazon Chime user\. | FA, UM | 
| `chime:DisassociatePhoneNumbersFromVoiceConnector` | Grants permission to disassociate phone numbers from the specified Amazon Chime Voice Connector\. | FA | 
| `chime:GetCDRBucket` | Grants permission to get details of a Call Detail Record S3 bucket associated with your Amazon Chime account\. | FA, RO | 
| `chime:GetGlobalSettings` | Grants permission to get global settings related to Amazon Chime for the AWS account, such as call detail records\. | FA | 
| `chime:GetPhoneNumber` | Grants permission to get details for the specified phone number\. | FA, UM, RO | 
| `chime:GetPhoneNumberOrder` | Grants permission to get details for the specified phone number order\. | FA, RO | 
| `chime:GetTelephonyLimits` | Grants permission to get telephony limits for the AWS account\. | FA | 
| `chime:GetVoiceConnector` | Grants permission to get details for the specified Amazon Chime Voice Connector\. | FA, RO | 
| `chime:GetVoiceConnectorOrigination` | Grants permission to get details of the origination settings for the specified Amazon Chime Voice Connector\. | FA, RO | 
| `chime:GetVoiceConnectorTermination` | Grants permission to get details of the termination settings for the specified Amazon Chime Voice Connector\. | FA, RO | 
| `chime:GetVoiceConnectorTerminationHealth` | Grants permission to get details of the termination health for the specified Amazon Chime Voice Connector\. | FA, RO | 
| `chime:ListCallingRegions` | Grants permission to list the calling regions available for the administrator's AWS account\. | FA, RO | 
| `chime:ListCDRBucket` | Grants permission to list Call Detail Record S3 buckets associated with your Amazon Chime account\. | FA, RO | 
| `chime:ListPhoneNumberOrders` | Grants permission to list the phone number orders for the account\. | FA, RO | 
| `chime:ListPhoneNumbers` | Grants permission to list the phone numbers under the administrator's AWS account\. | FA, UM, RO | 
| `chime:ListVoiceConnectors` | Grants permission to list the Amazon Chime Voice Connectors under the administrator's AWS account\. | FA, RO | 
| `chime:ListVoiceConnectorTerminationCredentials` | Grants permission to list the SIP termination credentials for the specified Amazon Chime Voice Connector\. | FA, RO | 
| `chime:PutVoiceConnectorOrigination` | Grants permission to update the origination settings for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:PutVoiceConnectorTermination` | Grants permission to update the termination settings for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:PutVoiceConnectorTerminationCredentials` | Grants permission to add SIP termination credentials for the specified Amazon Chime Voice Connector\. | FA | 
| `chime:RestorePhoneNumber` | Grants permission to restore the specified phone number from the deletion queue back into the phone number inventory\. | FA | 
| `chime:SearchAvailablePhoneNumbers` | Grants permission to search phone numbers available for ordering from the carrier\. | FA, RO | 
| `chime:UpdateGlobalSettings` | Grants permission to update the global settings related to Amazon Chime for the AWS account, such as call detail records\. | FA | 
| `chime:UpdatePhoneNumber` | Grants permission to update phone number details for the specified phone number\. | FA | 
| `chime:UpdateVoiceConnector` | Grants permission to update details for the specified Amazon Chime Voice Connector\. | FA | 
| **Amazon Chime Support** | 
| `chime:SubmitSupportRequest` | Grants permission to submit a customer service support request\. | FA, UM | 
| **AWS Account Delegation** \(\*\) Only used in conjunction with partner resellers\. | 
| `chime:AcceptDelegate` | \(Partner's customer\) Grants permission to accept the delegate invitation to share management of an Amazon Chime account with another AWS account\. \(\*\) | FA | 
| `chime:DeleteDelegate` | \(Partner and customer\) Grants permission to delete delegated AWS account management from your Amazon Chime account\. \(\*\) | FA | 
| `chime:ListDelegates` | \(Partner and customer\) Grants permission to list account delegate information associated with your Amazon Chime account\. \(\*\) | FA, UM, RO | 