# Automating Amazon Chime with EventBridge<a name="automating-chime-with-cloudwatch-events"></a>

Amazon EventBridge lets you automate your AWS services and respond automatically to system events, such as application availability issues or resource changes\. Events from AWS services are delivered to EventBridge in near real time\. You can write simple rules to specify the events that are of interest to you, and the automated actions to take when any of those events matches a rule\.

## Automating Amazon Chime Voice Connectors with EventBridge<a name="events-cvc"></a>

The actions that can be automatically triggered for Amazon Chime Voice Connectors include the following:
+ Invoking an AWS Lambda function
+ Launching an Amazon Elastic Container Service task
+ Relaying the event to Amazon Kinesis Video Streams
+ Activating an AWS Step Functions state machine
+ Notifying an Amazon SNS topic or an Amazon SQS queue

Some examples of using EventBridge with Amazon Chime Voice Connectors include:
+ Activating a Lambda function to download audio for a call after the call is ended\.
+ Launching an Amazon ECS task to enable real\-time transcription after a call is started\.

For more information, see the [Amazon EventBridge User Guide](https://docs.aws.amazon.com/eventbridge/latest/userguide/)\.

## Amazon Chime Voice Connector Streaming Events<a name="stream-events-cvc"></a>

Amazon Chime Voice Connectors support sending events to EventBridge when the events discussed in this section occur\.

### Amazon Chime Voice Connector Streaming Starts<a name="stream-start-cvc"></a>

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Video Streams starts\.

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

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Video Streams ends\.

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

Amazon Chime Voice Connectors send this event when media streaming to Kinesis Video Streams fails\.

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

## Automating the Amazon Chime SDK with EventBridge<a name="events-sdk"></a>

Some examples of using EventBridge with the Amazon Chime SDK include:
+ Updating metadata when an attendee joins or leaves an Amazon Chime SDK meeting\.
+ Implementing push notifications or rosters for an Amazon Chime SDK meeting\.

For more information, see the [Amazon EventBridge User Guide](https://docs.aws.amazon.com/eventbridge/latest/userguide/) and [Using the Amazon Chime SDK](https://docs.aws.amazon.com/chime/latest/dg/meetings-sdk.html) in the *Amazon Chime Developer Guide*\.

## Amazon Chime SDK Events<a name="sdk-events"></a>

The Amazon Chime SDK supports sending events to EventBridge when the events discussed in this section occur\.

### Amazon Chime SDK Meeting Starts<a name="sdk-start-mtg"></a>

The Amazon Chime SDK sends this event when a new meeting starts\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:MeetingStarted",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
  }
}
```

### Amazon Chime SDK Meeting Ends<a name="sdk-end-mtg"></a>

The Amazon Chime SDK sends this event when an active meeting ends\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:MeetingEnded",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
  }
}
```

### Amazon Chime SDK Attendee Is Added<a name="sdk-add-attendee"></a>

The Amazon Chime SDK sends this event when a new attendee is added to an active meeting\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeAdded",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333",
  }
}
```

### Amazon Chime SDK Attendee Is Removed<a name="sdk-remove-attendee"></a>

The Amazon Chime SDK sends this event when an attendee is removed from an active meeting\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeDeleted",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333",
  }
}
```

### Amazon Chime SDK Attendee Is Authorized<a name="sdk-auth-attendee"></a>

The Amazon Chime SDK sends this event when an existing attendee joins a meeting\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeAuthorized",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Joins a Meeting<a name="sdk-join-attendee"></a>

The Amazon Chime SDK sends this event when an existing attendee joins an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeJoined",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Leaves a Meeting<a name="sdk-leave-attendee"></a>

The Amazon Chime SDK sends this event when an existing attendee leaves an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeLeft",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Drops from a Meeting<a name="sdk-drop-attendee"></a>

The Amazon Chime SDK sends this event when an existing attendee drops from an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeDropped",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Starts Streaming Video<a name="sdk-attendee-video-start"></a>

The Amazon Chime SDK sends this event when an existing attendee starts streaming video\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeVideoStarted",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Stops Streaming Video<a name="sdk-attendee-video-stop"></a>

The Amazon Chime SDK sends this event when an existing attendee stops streaming video\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeVideoStopped",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Starts Sharing Screen<a name="sdk-attendee-screenshare-start"></a>

The Amazon Chime SDK sends this event when an existing attendee starts sharing their screen\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeScreenShareStarted",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Stops Sharing Screen<a name="sdk-attendee-screenshare-stop"></a>

The Amazon Chime SDK sends this event when an existing attendee stops sharing their screen\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeScreenShareStopped",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Content Joins a Meeting<a name="sdk-content-join"></a>

The Amazon Chime SDK sends this event when a content share joins an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeContentJoined",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Content Leaves a Meeting<a name="sdk-content-leave"></a>

The Amazon Chime SDK sends this event when a content share leaves an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeContentLeft",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Content Drops from a Meeting<a name="sdk-content-drop"></a>

The Amazon Chime SDK sends this event when a content share drops from an Amazon Chime SDK meeting using the specified network transport\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeContentDropped",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
    "networkType" "Voip"
  }
}
```

### Amazon Chime SDK Attendee Content Starts Streaming Video<a name="sdk-content-start-stream"></a>

The Amazon Chime SDK sends this event when a content share starts streaming video\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeContentVideoStarted",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```

### Amazon Chime SDK Attendee Content Stops Streaming Video<a name="sdk-content-stop-stream"></a>

The Amazon Chime SDK sends this event when a content share stops streaming video\.

**Example Event Data**  
The following is example data for this event\.  

```
{
  "version": "0",
  "source": "aws.chime",
  "account": "111122223333",
  "id": "12345678-1234-1234-1234-111122223333",
  "region": "us-east-1",
  "detail-type": "Chime Meeting State Change",
  "time": "yyyy-mm-ddThh:mm:ssZ",
  "resources": []
  "detail": {
    "version": "0",
    "eventType": "chime:AttendeeContentVideoStopped",
    "timestamp": 12344566754,
    "meetingId": "87654321-4321-4321-1234-111122223333",
    "attendeeId": "87654321-4321-4321-1234-111122223333",
    "externalUserId": "87654321-4321-4321-1234-111122223333"
  }
}
```