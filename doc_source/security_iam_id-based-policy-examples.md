# Amazon Chime Identity\-Based Policy Examples<a name="security_iam_id-based-policy-examples"></a>

By default, IAM users and roles don't have permission to create or modify Amazon Chime resources\. They also can't perform tasks using the AWS Management Console, AWS CLI, or AWS API\. An IAM administrator must create IAM policies that grant users and roles permission to perform specific API operations on the specified resources they need\. The administrator must then attach those policies to the IAM users or groups that require those permissions\.

To learn how to create an IAM identity\-based policy using these example JSON policy documents, see [Creating Policies on the JSON Tab](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-json-editor) in the *IAM User Guide*\.

**Topics**
+ [Policy Best Practices](#security_iam_service-with-iam-policy-best-practices)
+ [Using the Amazon Chime Console](#security_iam_id-based-policy-examples-console)
+ [Allow Users to View Their Own Permissions](#security_iam_id-based-policy-examples-view-own-permissions)
+ [Allow Users to Access User Management Actions](#security_iam_id-based-policy-examples-user-management)
+ [Allow Users to Access Amazon Chime SDK Actions](#security_iam_id-based-policy-examples-chime-sdk)

## Policy Best Practices<a name="security_iam_service-with-iam-policy-best-practices"></a>

Identity\-based policies are very powerful\. They determine whether someone can create, access, or delete Amazon Chime resources in your account\. These actions can incur costs for your AWS account\. When you create or edit identity\-based policies, follow these guidelines and recommendations:
+ **Get Started Using AWS Managed Policies** – To start using Amazon Chime quickly, use AWS managed policies to give your employees the permissions they need\. These policies are already available in your account and are maintained and updated by AWS\. For more information, see [Get Started Using Permissions With AWS Managed Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#bp-use-aws-defined-policies) in the *IAM User Guide*\.
+ **Grant Least Privilege** – When you create custom policies, grant only the permissions required to perform a task\. Start with a minimum set of permissions and grant additional permissions as necessary\. Doing so is more secure than starting with permissions that are too lenient and then trying to tighten them later\. For more information, see [Grant Least Privilege](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#grant-least-privilege) in the *IAM User Guide*\.
+ **Enable MFA for Sensitive Operations** – For extra security, require IAM users to use multi\-factor authentication \(MFA\) to access sensitive resources or API operations\. For more information, see [Using Multi\-Factor Authentication \(MFA\) in AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html) in the *IAM User Guide*\.
+ **Use Policy Conditions for Extra Security** – To the extent that it's practical, define the conditions under which your identity\-based policies allow access to a resource\. For example, you can write conditions to specify a range of allowable IP addresses that a request must come from\. You can also write conditions to allow requests only within a specified date or time range, or to require the use of SSL or MFA\. For more information, see [IAM JSON Policy Elements: Condition](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html) in the *IAM User Guide*\.

## Using the Amazon Chime Console<a name="security_iam_id-based-policy-examples-console"></a>

To access the Amazon Chime console, you must have a minimum set of permissions\. These permissions must allow you to list and view details about the Amazon Chime resources in your AWS account\. If you create an identity\-based policy that is more restrictive than the minimum required permissions, the console won't function as intended for entities \(IAM users or roles\) with that policy\.

To ensure that those entities can still use the Amazon Chime console, also attach the following AWS managed **AmazonChimeReadOnly** policy to the entities\. For more information, see [Adding Permissions to a User](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_change-permissions.html#users_change_permissions-add-console) in the *IAM User Guide*:

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

You don't need to allow minimum console permissions for users that are making calls only to the AWS CLI or the AWS API\. Instead, allow access to only the actions that match the API operation that you're trying to perform\.

## Allow Users to View Their Own Permissions<a name="security_iam_id-based-policy-examples-view-own-permissions"></a>

This example shows how you might create a policy that allows IAM users to view the inline and managed policies that are attached to their user identity\. This policy includes permissions to complete this action on the console or programmatically using the AWS CLI or AWS API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ViewOwnUserInfo",
            "Effect": "Allow",
            "Action": [
                "iam:GetUserPolicy",
                "iam:ListGroupsForUser",
                  "iam:ListAttachedUserPolicies",
                "iam:ListUserPolicies",
                "iam:GetUser"
            ],
            "Resource": ["arn:aws:iam::*:user/${aws:username}"]
        },
        {
            "Sid": "NavigateInConsole",
            "Effect": "Allow",
            "Action": [
                "iam:GetGroupPolicy",
                "iam:GetPolicyVersion",
                "iam:GetPolicy",
                "iam:ListAttachedGroupPolicies",
                "iam:ListGroupPolicies",
                "iam:ListPolicyVersions",
                "iam:ListPolicies",
                "iam:ListUsers"
            ],
            "Resource": "*"
        }
    ]
}
```

## Allow Users to Access User Management Actions<a name="security_iam_id-based-policy-examples-user-management"></a>

Use the AWS managed **AmazonChimeUserManagement** policy to grant users access to user management actions in the Amazon Chime console\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "chime:ListAccounts",
                "chime:GetAccount",
                "chime:GetAccountSettings",
                "chime:UpdateAccountSettings",
                "chime:ListUsers",
                "chime:GetUser",
                "chime:GetUserByEmail",
                "chime:InviteUsers",
                "chime:InviteUsersFromProvider",
                "chime:SuspendUsers",
                "chime:ActivateUsers",
                "chime:UpdateUserLicenses",
                "chime:ResetPersonalPIN",
                "chime:LogoutUser",
                "chime:ListDomains",
                "chime:GetDomain",
                "chime:ListDirectories",
                "chime:ListGroups",
                "chime:SubmitSupportRequest",
                "chime:ListDelegates",
                "chime:ListAccountUsageReportData",
                "chime:GetMeetingDetail",
                "chime:ListMeetingEvents",
                "chime:ListMeetingsReportData",
                "chime:GetUserActivityReportData",
                "chime:UpdateUser",
                "chime:BatchUpdateUser",
                "chime:BatchSuspendUser",
                "chime:BatchUnsuspendUser",
                "chime:AssociatePhoneNumberWithUser",
                "chime:DisassociatePhoneNumberFromUser",
                "chime:GetPhoneNumber",
                "chime:ListPhoneNumbers",
                "chime:GetUserSettings",
                "chime:UpdateUserSettings"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```

## Allow Users to Access Amazon Chime SDK Actions<a name="security_iam_id-based-policy-examples-chime-sdk"></a>

Use the AWS managed **AmazonChimeSDK** policy to grant users access to Amazon Chime SDK actions\. For more information, see [Using the Amazon Chime SDK](https://docs.aws.amazon.com/chime/latest/dg/meetings-sdk.html) in the *Amazon Chime Developer Guide*\.

```
{
  "Version": "2012-10-17",  
  "Statement": [
    {
      "Action": [
        "chime:CreateMeeting",
        "chime:DeleteMeeting",
        "chime:GetMeeting",
        "chime:ListMeetings",
        "chime:CreateAttendee",
        "chime:BatchCreateAttendee",
        "chime:DeleteAttendee",
        "chime:GetAttendee",
        "chime:ListAttendees"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
```