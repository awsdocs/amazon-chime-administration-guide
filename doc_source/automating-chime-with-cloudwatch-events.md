# Automating Amazon Chime with CloudWatch Events<a name="automating-chime-with-cloudwatch-events"></a>

Amazon CloudWatch Events lets you automate your AWS services and respond automatically to system events such as application availability issues or resource changes\. Events from AWS services are delivered to CloudWatch Events in near real time\. You can write simple rules to indicate which events are of interest to you, and what automated actions to take when an event matches a rule\.

## Automating Amazon Chime Voice Connectors with CloudWatch Events<a name="events-cvc"></a>

The actions that can be automatically triggered for Amazon Chime Voice Connectors include the following:
+ Invoking an AWS Lambda function
+ Launching an Amazon Elastic Container Service task
+ Relaying the event to Amazon Kinesis Data Streams
+ Activating an AWS Step Functions state machine
+ Notifying an Amazon SNS topic or an Amazon SQS queue

Some examples of using CloudWatch Events with Amazon Chime Voice Connectors include:
+ Activating a Lambda function to download audio for a call after the call is ended\.
+ Launching an Amazon ECS task to enable real\-time transcription after a call is started\.

For more information, see the [Amazon CloudWatch Events User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/)\.

## Amazon Chime Voice Connector Streaming Events<a name="stream-events-cvc"></a>

Amazon Chime Voice Connectors support sending events to CloudWatch Events when the following events occur:
+ [Amazon Chime Voice Connector Streaming Starts](#stream-start-cvc)
+ [Amazon Chime Voice Connector Streaming Ends](#stream-end-cvc)
+ [Amazon Chime Voice Connector Streaming Fails](#stream-fail-cvc)

### Amazon Chime Voice Connector Streaming Starts<a name="stream-start-cvc"></a>

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Data Streams starts\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "id": "12345678-1234-1234-1234-111122223333",
  "detail-type": "Chime VoiceConnector Streaming Status",
  "source": "aws.chime",
  "account": "111122223333",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "region": "us-east-1",
  "resources": [],
  "detail": {
       "streamingStatus":"STARTED",
       "voiceConnectorId":"abcdefghi",
       "transactionId":"12345678-1234-1234",
       "callId":"1112-2222-4333",
       "direction":"Inbound",
       "mediaType":"audio/L16",
       "startFragmentNumber":"1234567899444",
       "startTime":"yyyy-mm-ddThh:mm:ssZ",
       "streamArn":"arn:aws:kinesisvideo:us-east-1:123456:stream/ChimeVoiceConnector-abcdefghi-111aaa-22bb-33cc-44dd-111222/111122223333",
       "version":"0"
  }
}
```

### Amazon Chime Voice Connector Streaming Ends<a name="stream-end-cvc"></a>

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Data Streams ends\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "id": "12345678-1234-1234-1234-111122223333",
  "detail-type": "Chime VoiceConnector Streaming Status",
  "source": "aws.chime",
  "account": "111122223333",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "region": "us-east-1",
  "resources": [],
  "detail": {
       "streamingStatus":"ENDED",
       "voiceConnectorId":"abcdefghi",
       "transactionId":"12345678-1234-1234",
       "callId":"1112-2222-4333",
       "direction":"Inbound",
       "mediaType":"audio/L16",
       "startFragmentNumber":"1234567899444",
       "startTime":"yyyy-mm-ddThh:mm:ssZ",
       "endTime":"yyyy-mm-ddThh:mm:ssZ",
       "streamArn":"arn:aws:kinesisvideo:us-east-1:123456:stream/ChimeVoiceConnector-abcdefghi-111aaa-22bb-33cc-44dd-111222/111122223333",
       "version":"0"
  }
}
```

### Amazon Chime Voice Connector Streaming Fails<a name="stream-fail-cvc"></a>

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Data Streams fails\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "id": "12345678-1234-1234-1234-111122223333",
  "detail-type": "Chime VoiceConnector Streaming Status",
  "source": "aws.chime",
  "account": "111122223333",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "region": "us-east-1",
  "resources": [],
  "detail": {
       "streamingStatus":"FAILED",
       "voiceConnectorId":"abcdefghi",
       "transactionId":"12345678-1234-1234",
       "callId":"1112-2222-4333",
       "direction":"Inbound",
       "failTime":"yyyy-mm-ddThh:mm:ssZ",
       "failureReason": "Internal failure",
       "version":"0"
  }
}
```