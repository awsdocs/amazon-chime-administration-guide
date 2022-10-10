# Managing global settings in Amazon Chime<a name="manage-global"></a>

You use the Amazon Chime console to manage call detail record settings\.

## Configuring call detail records<a name="call-detail"></a>

Before you can configure call detail record settings for your Amazon Chime administrative account, you must first create an Amazon Simple Storage Service bucket\. The Amazon S3 bucket is used as the log destination for your call detail records\. When you configure your call detail record settings, you grant Amazon Chime read and write access to the Amazon S3 bucket in order to save and manage your data\. For more information about creating an Amazon S3 bucket, see [Getting started with Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) in the *Amazon Simple Storage Service User Guide*\.

You can configure call detail record settings for Amazon Chime Business Calling\. For more information about Amazon Chime Business Calling, see [Managing phone numbers in Amazon Chime](phone-numbers.md)\.

**To configure call detail record settings**

1. Create an Amazon S3 bucket by following the steps at [Getting started with Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) in the *Amazon Simple Storage Service User Guide*\.

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Global Settings**, choose **Call detail records**\.

1. Choose **Business Calling Configuration**\.

1. For **Log destination**, select the Amazon S3 bucket\.

1. Choose **Save**\.

You can stop logging call detail records at any time\.

**To stop logging call detail records**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Global Settings**, choose **Call detail records**\.

1. Choose **Disable logging** for the applicable configuration\.

## Amazon Chime Business Calling call detail records<a name="bc-cdr"></a>

When you choose to receive call detail records for Amazon Chime Business Calling, they are sent to your Amazon S3 bucket\. The following example shows the general format of an Amazon Chime Business Calling call detail record name\.

```
Amazon-Chime-Business-Calling-CDRs/json/111122223333/2019/03/01/123a4567-b890-1234-5678-cd90efgh1234_2019-03-01-17.10.00.020_1a234567-89bc-01d2-3456-e78f9g01234h
```

The following example shows the data that is represented in the call detail record name\.

```
Amazon-Chime-Business-Calling-CDRs/json/awsAccountID/year/month/day/conferenceID_connectionDate-callStartTime-callDetailRecordID
```

The following example shows the general format of an Amazon Chime Business Calling call detail record\.

```
{
    "SchemaVersion": "2.0",
    "CdrId": "1a234567-89bc-01d2-3456-e78f9g01234h",
    "ServiceCode": "AmazonChimeBusinessCalling",
    "ChimeAccountId": "12a3456b-7c89-012d-3456-78901e23fg45",
    "AwsAccountId": "111122223333",
    "ConferenceId": "123a4567-b890-1234-5678-cd90efgh1234",
    "ConferencePin": "XXXXXXXXXX",
    "OrganizerUserId": "1ab2345c-67de-8901-f23g-45h678901j2k",
    "OrganizerEmail": "jdoe@example.com",

    "CallerPhoneNumber": "+12065550100",
    "CallerCountry": "US",

    "DestinationPhoneNumber": "+12065550101",
    "DestinationCountry": "US",

    "ConferenceStartTimeEpochSeconds": "1556009595",
    "ConferenceEndTimeEpochSeconds": "1556009623",
    "StartTimeEpochSeconds": "1556009611",
    "EndTimeEpochSeconds": "1556009623",
    "BillableDurationSeconds": "24",
    "BillableDurationMinutes": ".4",
    "Direction": "Outbound"
}
```