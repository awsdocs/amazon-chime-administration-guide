# Managing Global Settings in Amazon Chime<a name="manage-global"></a>

Manage call detail record settings from the Amazon Chime console\.

## Configuring Call Detail Records<a name="call-detail"></a>

Before you can configure call detail record settings for your Amazon Chime administrative account, you must first create an Amazon Simple Storage Service bucket\. The Amazon S3 bucket is used as the log destination for your call detail records\. When you configure your call detail record settings, you grant Amazon Chime read and write access to the Amazon S3 bucket in order to save and manage your data\. For more information about creating an Amazon S3 bucket, see [Getting Started with Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) in the *Amazon Simple Storage Service Getting Started Guide*\.

You can also configure call detail record settings for Amazon Chime Business Calling and Amazon Chime Voice Connectors\. For more information about Amazon Chime Business Calling and Amazon Chime Voice Connectors, see [Managing Phone Numbers in Amazon Chime](manage-phone.md)\.

**To configure call detail record settings**

1. Create an Amazon S3 bucket by following the steps at [Getting Started with Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) in the *Amazon Simple Storage Service Getting Started Guide*\.

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Global Settings**, choose **Call detail records**\.

1. For **Log destination**, select the Amazon S3 bucket\.

1. Choose **Save**\.