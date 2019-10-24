# Streaming Amazon Chime Voice Connector Media to Kinesis<a name="start-kinesis-vc"></a>

You can stream phone call audio from Amazon Chime Voice Connectors to Amazon Kinesis Video Streams for analytics, machine learning, and other processing\. Developers can store and encrypt audio data in Kinesis Video Streams, and access the data using the Kinesis Video Streams API operation\. For more information, see the [https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/what-is-kinesis-video.html](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/what-is-kinesis-video.html)\.

Use the Amazon Chime console to start media streaming for your Amazon Chime Voice Connector\. When media streaming is started, your Amazon Chime Voice Connector uses an IAM service\-linked role to grant permissions to stream media to Kinesis Video Streams\. Then, call audio from each Amazon Chime Voice Connector telephone call leg is streamed in real time to separate Kinesis Video Streams\.

Use the Kinesis Video Streams Parser Library to download the media streams sent from your Amazon Chime Voice Connector\. Filter the streams by the following persistent fragments metadata\.
+ TransactionId
+ VoiceConnectorId

For more information, see [Kinesis Video Streams Parser Library](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/parser-library.html) and [Using Streaming Metadata with Kinesis Video Streamss](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/how-meta.html) in the *Amazon Kinesis Video Streams Developer Guide*\.

For more information about using IAM service\-linked roles with Amazon Chime Voice Connectors, see [Using Roles to Stream Amazon Chime Voice Connector Media to Kinesis](using-service-linked-roles-stream.md)\. For more information about using CloudWatch with Amazon Chime, see [Monitoring Amazon Chime](monitoring-overview.md)\.

When you enable media streaming for your Amazon Chime Voice Connector, Amazon Chime creates an IAM service\-linked role called AWSServiceRoleForAmazonChimeVoiceConnector\.

**To start media streaming for your Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose the name of the Amazon Chime Voice Connector\.

1. Choose **Streaming**\.

1. For **Sending to Kinesis Video Streams**, choose **Start**\.

1. Select a **Data retention period**\.

1. Choose **Save**\.

Turn off media streaming from the Amazon Chime console\. If you no longer need to use media streaming for any of your Amazon Chime Voice Connectors, we recommend that you also delete the related service\-linked role\. For more information, see [Deleting a Service\-Linked Role for Amazon Chime Voice Connectors](using-service-linked-roles-stream.md#delete-service-linked-role-stream)\.

**To stop media streaming for your Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose the name of the Amazon Chime Voice Connector\.

1. Choose **Streaming**\.

1. For **Sending to Kinesis Video Streams**, choose **Stop**\.

1. Choose **Save**\.