# Cross\-service confused deputy prevention<a name="confused-deputy"></a>

The confused deputy problem is an information security issue that occurs when an entity without permission to perform an action calls a more\-privileged entity to perform the action\. This can allow malicious actors to run commands or modify resources they otherwise would not have permission to run or access\. For more information, see [The confused deputy problem](https://docs.aws.amazon.com/IAM/latest/UserGuide/confused-deputy.html) in the *AWS Identity and Access Management User Guide*\.

In AWS, cross\-service impersonation can lead to a confused deputy scenario\. Cross\-service impersonation happens when one service \(the *calling service*\) calls another service \(the *called service*\)\. A malicious actor can use the calling service to alter resources in another service by using permissions that they normally would not have\.

AWS provides service principals with managed access to resources on your account to help you protect your resources' security\. We recommend using the `aws:SourceAccount` global condition context key in your resource policies\. These keys limit the permissions that Amazon Chime gives another service to that resource\.

The following example shows an S3 bucket policy that uses the `aws:SourceAccount` global condition context key in the configured `CallDetailRecords` S3 bucket to help prevent the confused deputy problem\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AmazonChimeAclCheck668426",
            "Effect": "Allow",
            "Principal": {
                "Service": "chime.amazonaws.com"
            },
            "Action": "s3:GetBucketAcl",
            "Resource": "arn:aws:s3:::your-cdr-bucket"
        },
        {
            "Sid": "AmazonChimeWrite668426",
            "Effect": "Allow",
            "Principal": {
                "Service": "chime.amazonaws.com"
            },
            "Action": "s3:PutObject",
            "Resource": "arn:aws:s3:::your-cdr-bucket/*",
            "Condition": {
                "StringEquals": {
                    "s3:x-amz-acl": "bucket-owner-full-control",
                    "aws:SourceAccount": "112233446677" 
                }
            }
        }
    ]
}
```