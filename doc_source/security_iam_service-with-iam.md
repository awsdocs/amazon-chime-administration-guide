# How Amazon Chime works with IAM<a name="security_iam_service-with-iam"></a>

Before you use IAM to manage access to Amazon Chime, you should understand what IAM features are available to use with Amazon Chime\. To get a high\-level view of how Amazon Chime and other AWS services work with IAM, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) in the *IAM User Guide*\.

**Topics**
+ [Amazon Chime identity\-based policies](#security_iam_service-with-iam-id-based-policies)
+ [Resources](#security_iam_service-with-iam-id-based-policies-resources)
+ [Examples](#security_iam_service-with-iam-id-based-policies-examples)

## Amazon Chime identity\-based policies<a name="security_iam_service-with-iam-id-based-policies"></a>

With IAM identity\-based policies, you can specify allowed or denied actions and resources as well as the conditions under which actions are allowed or denied\. Amazon Chime supports specific actions, resources, and condition keys\. To learn about all of the elements that you use in a JSON policy, see [IAM JSON policy elements reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html) in the *IAM User Guide*\.

### Actions<a name="security_iam_service-with-iam-id-based-policies-actions"></a>

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Action` element of a JSON policy describes the actions that you can use to allow or deny access in a policy\. Policy actions usually have the same name as the associated AWS API operation\. There are some exceptions, such as *permission\-only actions* that don't have a matching API operation\. There are also some operations that require multiple actions in a policy\. These additional actions are called *dependent actions*\.

Include actions in a policy to grant permissions to perform the associated operation\.

### Condition keys<a name="security_iam_service-with-iam-id-based-policies-conditionkeys"></a>

Amazon Chime does not provide any service\-specific condition keys\. To see all AWS global condition keys, see [AWS Global Condition Context Keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html) in the *IAM User Guide*\.

## Resources<a name="security_iam_service-with-iam-id-based-policies-resources"></a>

Amazon Chime does not support specifying resource ARNs in a policy\.

## Examples<a name="security_iam_service-with-iam-id-based-policies-examples"></a>

To view examples of Amazon Chime identity\-based policies, see [Amazon Chime identity\-based policy examples](security_iam_id-based-policy-examples.md)\.