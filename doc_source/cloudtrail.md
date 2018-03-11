# Log Amazon Chime Administration Calls with AWS CloudTrail<a name="cloudtrail"></a>

The Amazon Chime administration console is integrated with AWS CloudTrail\. CloudTrail is a service that captures API calls made by or on behalf of Amazon Chime in your AWS account and delivers the log files to an Amazon S3 bucket that you specify\. CloudTrail captures all API calls from the Amazon Chime administration console and logs the responses from mutating calls\. For example, listDomain is read\-only and you only see the request in CloudTrail\. However, with addDomain, you see both the request and the response\. Using the information collected by CloudTrail, you can determine which requests were made, the source IP address for the request, who made the request, and when it was made\. For more information, including how to configure and enable CloudTrail, see the [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)\.

When CloudTrail logging is enabled in your AWS account, API calls made from the Amazon Chime administration console on your behalf are tracked in log files\. These records are written together with other AWS service records in a log file\. CloudTrail determines when to create and write to a new file based on time period and file size\. All actions taken in the administration console use API calls and are logged by CloudTrail\. You can store your log files in your bucket for as long as you want, or you can define Amazon S3 lifecycle rules to archive or delete log files automatically\. By default, your log files are encrypted using Amazon S3 server\-side encryption \(SSE\)\. To take quick action upon log file delivery, you can choose to have CloudTrail publish Amazon SNS notifications when new log files are delivered\. For more information, see [Configuring Amazon SNS Notifications for CloudTrail](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/configure-sns-notifications-for-cloudtrail.html)\. You can also aggregate AWS Directory Service log files from multiple AWS Regions and AWS accounts into a single S3 bucket\. For more information, see [Receiving CloudTrail Log Files from Multiple Regions](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html)\.

CloudTrail log files can contain one or more log entries, with each entry comprised of multiple JSON\-formatted events\. A log entry represents a single request and contains information about the action taken, who generated the request, where they were when they made the request, system information, and information that varies depending on the type of request\. For example, the addDomain call includes information on the domain the user is adding\. Every log entry also contains information about who generated the request\. The identity information in the log helps you determine whether the request was made with root or IAM user credentials, with temporary security credentials for a role or federated user, or by another AWS service\. For more information, see the **userIdentity** field in the [CloudTrail Log Event Reference](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference.html)\.

Log entries are not in any particular order and are not an ordered stack trace of the public API calls\. Entries for Amazon Chime are identified by the **chime\.amazonaws\.com** event source\. Sensitive information, such as passwords, authentication tokens, file comments, and file contents, are redacted in log entries\.

If you have configured Active Directory for your Amazon Chime account, see [Logging AWS Directory Service API Calls Using CloudTrail](http://docs.aws.amazon.com/directoryservice/latest/devguide/cloudtrail_logging.html)\. This describes how to monitor for issues that might affect your Amazon Chime users’ ability to sign in\. 

The following is an example of a CloudTrail log entry for Amazon Chime:

```
{"eventVersion":"1.05",
         "userIdentity":{  
            "type":"IAMUser",
            "principalId":" AAAAAABBBBBBBBEXAMPLE",
            "arn":"arn:aws:iam::123456789012:user/Alice ",
            "accountId":"0123456789012",
            "accessKeyId":"AAAAAABBBBBBBBEXAMPLE",
            "sessionContext":{  
               "attributes":{  
                  "mfaAuthenticated":"false",
                  "creationDate":"2017-07-24T17:57:43Z"
               },
               "sessionIssuer":{  
                  "type":"Role",
                  "principalId":"AAAAAABBBBBBBBEXAMPLE",
                  "arn":"arn:aws:iam::123456789012:role/Joe",
                  "accountId":"123456789012",
                  "userName":"Joe"
               }
            }
         } ,
         "eventTime":"2017-07-24T17:58:21Z",
         "eventSource":"chime.amazonaws.com",
         "eventName":"AddDomain",
         "awsRegion":"us-east-1",
         "sourceIPAddress":"72.21.198.64",
         "userAgent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36",
         "errorCode":"ConflictException",
         "errorMessage":"Request could not be completed due to a conflict",
         "requestParameters":{  
            "domainName":"example.com",
            "accountId":"11aaaaaa1-1a11-1111-1a11-aaadd0a0aa00"
         },
         "responseElements":null,
         "requestID":"be1bee1d-1111-11e1-1eD1-0dc1111f1ac1",
         "eventID":"00fbeee1-123e-111e-93e3-11111bfbfcc1",
         "eventType":"AwsApiCall",
         "recipientAccountId":"123456789012"
      }
```