# Monitoring Amazon Chime with Amazon CloudWatch<a name="monitoring-cloudwatch"></a>

You can monitor Amazon Chime using CloudWatch, which collects raw data and processes it into readable, near real\-time metrics\. These statistics are kept for 15 months, so that you can access historical information and gain a better perspective about how your web application or service is performing\. You can also set alarms that watch for certain thresholds, and send notifications or take actions when those thresholds are met\. For more information, see the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\.

## CloudWatch Metrics for Amazon Chime<a name="cw-metrics"></a>

Amazon Chime sends the following metrics and dimensions to CloudWatch\.

The `AWS/ChimeVoiceConnector` namespace includes the following metrics for phone numbers assigned to your AWS account and to Amazon Chime Voice Connectors\.


| Metric | Description | 
| --- | --- | 
|  `InboundCallAttempts`  |  The number of inbound calls attempted\. Units: Count  | 
|  `InboundCallFailures`  |  The number of inbound call failures\. Units: Count  | 
|  `InboundCallsAnswered`  |  The number of inbound calls that are answered\. Units: Count  | 
|  `InboundCallsActive`  |  The number of inbound calls that are currently active\. Units: Count  | 
|  `OutboundCallAttempts`  |  The number of outbound calls attempted\. Units: Count  | 
|  `OutboundCallFailures`  |  The number of outbound call failures\. Units: Count  | 
|  `OutboundCallsAnswered`  |  The number of outbound calls that are answered\. Units: Count  | 
|  `OutboundCallsActive`  |  The number of outbound calls that are currently active\. Units: Count  | 
|  `Throttles`  |  The number of times your account is throttled when attempting to make a call\. Units: Count  | 
|  `Sip1xxCodes`  |  The number of SIP messages with 1xx\-level status codes\. Units: Count  | 
|  `Sip2xxCodes`  |  The number of SIP messages with 2xx\-level status codes\. Units: Count  | 
|  `Sip3xxCodes`  |  The number of SIP messages with 3xx\-level status codes\. Units: Count  | 
|  `Sip4xxCodes`  |  The number of SIP messages with 4xx\-level status codes\. Units: Count  | 
|  `Sip5xxCodes`  |  The number of SIP messages with 5xx\-level status codes\. Units: Count  | 
|  `Sip6xxCodes`  |  The number of SIP messages with 6xx\-level status codes\. Units: Count  | 

## CloudWatch Dimensions for Amazon Chime<a name="cw-dimensions"></a>

The CloudWatch dimensions that you can use with Amazon Chime are listed as follows\.


| Dimension | Description | 
| --- | --- | 
|  `VoiceConnectorId`  |  The identifier of the Amazon Chime Voice Connector to display metrics for\.  | 
|  `Region`  |  The AWS Region associated with the event\.  | 

## CloudWatch Logs for Amazon Chime<a name="cw-logs"></a>

You can send Amazon Chime Voice Connector metrics to CloudWatch Logs\. For more information, see [Editing Amazon Chime Voice Connector Settings](voice-connectors.md#edit-voicecon)\.

**SIP Message Logs**  
You can opt to receive SIP message logs for your Amazon Chime Voice Connector\. When you do, Amazon Chime captures inbound and outbound SIP messages and sends them to a CloudWatch Logs log group that is created for you\. The log group name is `/aws/ChimeVoiceConnectorSipMessages/${VoiceConnectorID}`\. The following fields are included in the logs, in JSON format\.


| Field | Description | 
| --- | --- | 
|  voice\_connector\_id  |  The Amazon Chime Voice Connector ID\.  | 
|  aws\_region  |  The AWS Region associated with the event\.  | 
|  event\_timestamp  |  The time at which the message is captured, in number of milliseconds since the UNIX Epoch \(midnight on Jan 1 1970\) in UTC\.  | 
|  call\_id  |  The Amazon Chime Voice Connector call ID\.  | 
|  sip\_message  |  The full SIP message that is captured\.  | 