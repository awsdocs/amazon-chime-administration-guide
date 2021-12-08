# Security in Amazon Chime<a name="security"></a>

Cloud security at AWS is the highest priority\. As an AWS customer, you benefit from a data center and network architecture that is built to meet the requirements of the most security\-sensitive organizations\.

Security is a shared responsibility between AWS and you\. The [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) describes this as security *of* the cloud and security *in* the cloud:
+ **Security of the cloud** – AWS is responsible for protecting the infrastructure that runs AWS services in the AWS Cloud\. AWS also provides you with services that you can use securely\. Third\-party auditors regularly test and verify the effectiveness of our security as part of the [AWS Compliance Programs](http://aws.amazon.com/compliance/programs/)\. To learn about the compliance programs that apply to Amazon Chime, see [AWS Services in Scope by Compliance Program](http://aws.amazon.com/compliance/services-in-scope/)\.
+ **Security in the cloud** – Your responsibility is determined by the AWS service that you use\. You are also responsible for other factors including the sensitivity of your data, your company’s requirements, and applicable laws and regulations\. 

This documentation helps you understand how to apply the shared responsibility model when using Amazon Chime\. The following topics show you how to configure Amazon Chime to meet your security and compliance objectives\. You also learn how to use other AWS services that help you to monitor and secure your Amazon Chime resources\. 

**Topics**
+ [Identity and access management for Amazon Chime](security-iam.md)
+ [How Amazon Chime works with IAM](security_iam_service-with-iam.md)
+ [Amazon Chime resource\-based policies](#security_iam_service-with-iam-resource-based-policies)
+ [Authorization based on Amazon Chime tags](#security_iam_service-with-iam-tags)
+ [Amazon Chime IAM roles](#security_iam_service-with-iam-roles)
+ [Amazon Chime identity\-based policy examples](security_iam_id-based-policy-examples.md)
+ [Troubleshooting Amazon Chime identity and access](security_iam_troubleshoot.md)
+ [Using service\-linked roles for Amazon Chime](using-service-linked-roles.md)
+ [Logging and monitoring in Amazon Chime](monitoring-overview.md)
+ [Compliance validation for Amazon Chime](compliance.md)
+ [Resilience in Amazon Chime](disaster-recovery-resiliency.md)
+ [Infrastructure security in Amazon Chime](infrastructure-security.md)
+ [Understanding Amazon Chime automatic updates](chime-auto-update.md)

## Amazon Chime resource\-based policies<a name="security_iam_service-with-iam-resource-based-policies"></a>

Amazon Chime does not support resource\-based policies\.

## Authorization based on Amazon Chime tags<a name="security_iam_service-with-iam-tags"></a>

Amazon Chime does not support tagging resources or controlling access based on tags\.

## Amazon Chime IAM roles<a name="security_iam_service-with-iam-roles"></a>

An [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) is an entity within your AWS account that has specific permissions\.

### Using temporary credentials with Amazon Chime<a name="security_iam_service-with-iam-roles-tempcreds"></a>

You can use temporary credentials to sign in with federation, assume an IAM role, or to assume a cross\-account role\. You obtain temporary security credentials by calling AWS STS API operations such as [AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) or [GetFederationToken](https://docs.aws.amazon.com/STS/latest/APIReference/API_GetFederationToken.html)\. 

Amazon Chime supports using temporary credentials\. 

### Service\-linked roles<a name="security_iam_service-with-iam-roles-service-linked"></a>

[Service\-linked roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role) allow AWS services to access resources in other services that complete actions on your behalf\. Service\-linked roles appear in your IAM account, and the services own the roles\. An IAM administrator can view but not edit the permissions for service\-linked roles\.

Amazon Chime supports service\-linked roles\. For details about creating or managing Amazon Chime service\-linked roles, see [Using service\-linked roles for Amazon Chime](using-service-linked-roles.md)\.

### Service roles<a name="security_iam_service-with-iam-roles-service"></a>

This feature allows a service to assume a [service role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service roles appear in your IAM account and are owned by the account\. This means that an IAM administrator can change the permissions for this role\. However, doing so might break the functionality of the service\.

Amazon Chime does not support service roles\. 