# Managing Amazon Chime Voice Connectors<a name="voice-connectors"></a>

You can integrate an Amazon Chime Voice Connector with an existing phone system\. After you create an Amazon Chime Voice Connector, edit the settings to integrate it\. Then, assign phone numbers to the Amazon Chime Voice Connector\. You can provision phone numbers for your Amazon Chime Voice Connector from your Amazon Chime **Phone number management** inventory\. For more information, see [Provisioning Phone Numbers](provision-phone.md)\.

You can also create an Amazon Chime Voice Connector group for your account, and add Amazon Chime Voice Connectors to it\. You can include Amazon Chime Voice Connectors created in different AWS Regions in your group to create a fault\-tolerant mechanism for fallback if availability events occur\. For more information, see [Managing Amazon Chime Voice Connector Groups](voice-connector-groups.md)\.

**Topics**
+ [Before you Begin](#vc-prereq)
+ [Creating an Amazon Chime Voice Connector](create-voicecon.md)
+ [Editing Amazon Chime Voice Connector Settings](edit-voicecon.md)
+ [Assigning and Unassigning Amazon Chime Voice Connector Phone Numbers](assign-voicecon.md)
+ [Deleting an Amazon Chime Voice Connector](delete-voicecon.md)
+ [Managing Amazon Chime Voice Connector Groups](voice-connector-groups.md)
+ [Streaming Amazon Chime Voice Connector Media to Kinesis](start-kinesis-vc.md)

## Before you Begin<a name="vc-prereq"></a>

To use an Amazon Chime Voice Connector, you must have an IP Private Branch Exchange \(PBX\), Session Border Controller \(SBC\), or other voice infrastructure with internet access that supports Session Initiation Protocol \(SIP\)\. Make sure to confirm that you have sufficient bandwidth to support peak call volume\. For information about bandwidth requirements, see [Bandwidth Requirements](network-config.md#bandwidth)\.

To ensure security for calls sent from AWS to your on\-premises phone system, we recommend configuring a SBC between AWS and your phone system\. Whitelist SIP traffic to the SBC from the Amazon Chime Voice Connector signaling and media IP addresses\. For more information, see the recommended ports and protocols for [Amazon Chime Voice Connector](network-config.md#cvc)\.

Amazon Chime Voice Connectors expect phone numbers to be in E\.164 format\.