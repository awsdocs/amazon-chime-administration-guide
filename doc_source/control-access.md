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

To create your own policies, review the available [Actions Defined by Amazon Chime](https://docs.aws.amazon.com/IAM/latest/UserGuide/list_amazonchime.html#amazonchime-actions-as-permissions) in the *IAM User Guide* for a list of all of the actions that you can allow or deny in your policy\. For more information about managing and creating IAM policies, see [Managing IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage.html)\. For information about how to attach managed policies to an IAM user, see [Attaching and Detaching IAM Policies ](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html)\.

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
         "chime:ListDomains",
         "chime:GetDomain",
         "chime:ListGroups",
         "chime:ListDirectories",
         "chime:ListCDRBucket",
         "chime:GetCDRBucket",
         "chime:ListDelegates",
         "chime:GetAccountResource",
         "chime:ListAccountUsageReportData",
         "chime:GetUserActivityReportData",
         "chime:GetGlobalSettings",
         "chime:GetPhoneNumber",
         "chime:GetPhoneNumberOrder",
         "chime:GetPhoneNumberSettings",
         "chime:GetUserSettings",
         "chime:GetVoiceConnector",
         "chime:GetVoiceConnectorOrigination",
         "chime:GetVoiceConnectorTermination",
         "chime:GetVoiceConnectorTerminationHealth",
         "chime:GetVoiceConnectorStreamingConfiguration",
         "chime:GetVoiceConnectorLoggingConfiguration",
         "chime:GetVoiceConnectorGroup",
         "chime:ListPhoneNumberOrders",
         "chime:ListPhoneNumbers",
         "chime:ListVoiceConnectorTerminationCredentials",
         "chime:ListVoiceConnectors",
         "chime:ListVoiceConnectorGroups",
         "chime:SearchAvailablePhoneNumbers",
         "chime:GetTelephonyLimits",
         "chime:ListCallingRegions",
         "chime:GetBot",
         "chime:ListBots",
         "chime:GetEventsConfiguration"
       ],
       "Effect": "Allow",
       "Resource": "*"
     }
   ]
 }
```