# Using roles with live transcription<a name="using-service-linked-roles-transcription"></a>

The information in the following sections explains how to create and manage a service\-linked role for Amazon Chime live transcription\. For more information about the live transcription service, see [Using Amazon Chime SDK live transcription](https://docs.aws.amazon.com/chime/latest/dg/meeting-transcription.html)\.

**Topics**
+ [Service\-Linked Role Permissions for Amazon Chime Live Transcription](#service-linked-role-permissions-transcription)
+ [Creating a Service\-Linked Role for Amazon Chime Live Transcription](#create-service-linked-role-transcription)
+ [Editing a Service\-Linked Role for Amazon Chime Live Transcription](#edit-slr)
+ [Deleting a Service\-Linked Role for Amazon Chime Live Transcription](#delete-slr)
+ [Supported Regions for Amazon Chime Service\-Linked Roles](#slr-regions-transcription)

## Service\-Linked Role Permissions for Amazon Chime Live Transcription<a name="service-linked-role-permissions-transcription"></a>

Amazon Chime Live Transcription uses a service\-linked role named **AWSServiceRoleForAmazonChimeTranscription – Allows Amazon Chime to access Amazon Transcribe and Amazon Transcribe Medical on your behalf\.**

The AWSServiceRoleForAmazonChimeTranscription service\-linked role trusts the following services to assume the role:
+ `transcription.chime.amazonaws.com`

The role permissions policy allows Amazon Chime to complete the following actions on the specified resources:
+ Action: `transcribe:StartStreamTranscription` on `all AWS resources`
+ Action: `transcribe:StartMedicalStreamTranscription` on `all AWS resources`

You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. For more information, see [Service\-Linked Role Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#service-linked-role-permissions) in the *IAM User Guide*\.

## Creating a Service\-Linked Role for Amazon Chime Live Transcription<a name="create-service-linked-role-transcription"></a>

You use the IAM console to create a service\-linked role with the **Chime Transcription** use case\.

**Note**  
You must have IAM administrative permissions to complete these steps\. If you don't, contact a system administrator\.

**To create the role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane of the IAM console, choose **Roles**, then choose **Create role**\.

1. Choose the **AWS Service** role type, then choose **Chime**, then choose **Chime Transcription**\.

1. Choose **Next**\.

1. Choose **Next**\.

1. Edit the description as needed, then choose **Create role**\.

You can also use the AWS CLI or the AWS API to create a service\-linked role named transcription\.chime\.amazonaws\.com\. 

In the CLI, run this command: `aws iam create-service-linked-role --aws-service-name transcription.chime.amazonaws.com`\.

For more information, see [Creating a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#create-service-linked-role) in the *IAM User Guide*\. If you delete this service\-linked role, you can use this same process to create the role again\.

## Editing a Service\-Linked Role for Amazon Chime Live Transcription<a name="edit-slr"></a>

Amazon Chime does not allow you to edit the AWSServiceRoleForAmazonChimeTranscription service\-linked role\. After you create a service\-linked role, you cannot change the name of the role because various entities might reference the role\. However, you can use IAM to edit the role's description\. For more information, see [Editing a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#edit-service-linked-role) in the *IAM User Guide*\.

## Deleting a Service\-Linked Role for Amazon Chime Live Transcription<a name="delete-slr"></a>

If you no longer need to use a feature or service that requires a service\-linked role, we recommend that you delete that role\. That way you don’t have an unused entity that is not actively monitored or maintained\.

**To manually delete the service\-linked role using IAM**

Use the IAM console, the AWS CLI, or the AWS API to delete the AWSServiceRoleForAmazonChimeTranscription service\-linked role\. For more information, see [Deleting a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#delete-service-linked-role) in the *IAM User Guide*\.

## Supported Regions for Amazon Chime Service\-Linked Roles<a name="slr-regions-transcription"></a>

Amazon Chime supports using service\-linked roles in all of the regions where the service is available\. For more information, see [Amazon Chime endpoints and quotas](https://docs.aws.amazon.com/general/latest/gr/chime.html#chime_region), and [Using Amazon Chime SDK media Regions](https://docs.aws.amazon.com/chime/latest/dg/chime-sdk-meetings-regions.html)\.