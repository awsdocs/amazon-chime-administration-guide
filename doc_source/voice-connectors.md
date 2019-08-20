# Working with Amazon Chime Voice Connectors<a name="voice-connectors"></a>

You can integrate an Amazon Chime Voice Connector with an existing phone system\. Amazon Chime Voice Connectors are limited to three per account by default\.

After you create an Amazon Chime Voice Connector, edit the settings to integrate with your existing phone system\. Then, assign phone numbers to the Amazon Chime Voice Connector\. You can provision phone numbers for your Amazon Chime Voice Connector from your Amazon Chime **Phone number management** inventory\. For more information, see [Provisioning Phone Numbers](phone-numbers.md#provision-phone)\.

**Topics**
+ [Before you Begin](#vc-prereq)
+ [Creating an Amazon Chime Voice Connector](#create-voicecon)
+ [Editing Amazon Chime Voice Connector Settings](#edit-voicecon)
+ [Assigning and Unassigning Amazon Chime Voice Connector Phone Numbers](#assign-voicecon)
+ [Deleting an Amazon Chime Voice Connector](#delete-voicecon)

## Before you Begin<a name="vc-prereq"></a>

To use an Amazon Chime Voice Connector, you must have an IP Private Branch Exchange \(PBX\), Session Border Controller \(SBC\), or other voice infrastructure with internet access that supports Session Initiation Protocol \(SIP\)\. Make sure to confirm that you have sufficient bandwidth to support peak call volume\. For information about bandwidth requirements, see [Bandwidth Requirements](network-config.md#bandwidth)\.

To ensure security for calls sent from AWS to your on\-premises phone system, we recommend configuring a SBC between AWS and your phone system\. Whitelist SIP traffic to the SBC from the Amazon Chime Voice Connector signaling and media IP addresses\. For more information, see the recommended ports and protocols for [Amazon Chime Voice Connector](network-config.md#cvc)\.

Amazon Chime Voice Connectors expect phone numbers to be in E\.164 format\.

## Creating an Amazon Chime Voice Connector<a name="create-voicecon"></a>

Create an Amazon Chime Voice Connector from the Amazon Chime console\.

**To create an Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose **Create new voice connector**\.

1. For **Voice connector name**, enter a name for the Amazon Chime Voice Connector\.

1. For **Encryption**, select **Enabled** or **Disabled**\.

1. Choose **Create**\.

**Note**  
Enabling encryption configures your Amazon Chime Voice Connector to use TLS transport for SIP signaling and Secure RTP \(SRTP\) for media\. Inbound calls use TLS transport, and unencrypted outbound calls are blocked\.

## Editing Amazon Chime Voice Connector Settings<a name="edit-voicecon"></a>

To finish setting up your Amazon Chime Voice Connector, edit the settings from the Amazon Chime console\.

Set up your calling plan and caller ID options under the termination settings\. You can also specify the IP addresses allowed to make calls using your Amazon Chime Voice Connector, and require credentials for making outbound calls to your Amazon Chime Voice Connector\. If no credentials are specified, no authentication is required\.

Under the origination settings, configure inbound routes for your SIP hosts to receive inbound calls\. Inbound calls are routed to hosts in your SIP infrastructure by the priority and weight you set for each host\. Calls are routed in priority order first, with 1 being the highest priority\. If hosts are equal in priority, calls are distributed among them based on their relative weight\.

**Note**  
Encryption\-enabled Voice Connectors use TLS \(TCP\) protocol for all calls\.

**To edit Amazon Chime Voice Connector settings**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose the name of the Amazon Chime Voice Connector to edit\.

1. Edit your settings as follows:

   1. \(Optional\) Choose **General** to update the **Voice connector name**, and enable or disable encryption\.

   1. Choose **Termination settings**, and select **Enabled**\.

   1. \(Optional\) For **Allowlist**, choose **New**, enter the CIDR notations and values to allowlist, and choose **Add**\.

   1. For **Calling plan**, select the country or countries to add to your calling plan\.

   1. \(Optional\) For **Credentials**, choose **New**, enter a user name and password, and choose **Save**\. Your credentials are updated immediately\.

   1. \(Optional\) For **Caller ID**, choose **Edit**, select a caller ID phone number, and choose **Save**\.

   1. Choose **Save** again\.

   1. Choose **Origination settings**, and select **Enabled**\.

   1. For **Inbound routes**, choose **New**\.

   1. Enter the values for **Host**, **Port**, **Protocol**, **Priority**, and **Weight**\.

   1. Choose **Add**\.

   1. Choose **Save**\.

   1. Choose **Phone numbers**\.

   1. Select one or more phone numbers to assign to the Amazon Chime Voice Connector\.

   1. Choose **Assign**\.

For more information about assigning phone numbers to an Amazon Chime Voice Connector, see [Assigning and Unassigning Amazon Chime Voice Connector Phone Numbers](#assign-voicecon)\.

## Assigning and Unassigning Amazon Chime Voice Connector Phone Numbers<a name="assign-voicecon"></a>

You can assign up to 25 phone numbers to an Amazon Chime Voice Connector\.

**To assign phone numbers to an Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose the name of the Amazon Chime Voice Connector\.

1. Choose **Phone numbers**\.

1. Select one or more phone numbers to assign to the Amazon Chime Voice Connector\.

1. Choose **Assign**\.

**To unassign phone numbers from an Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose the name of the Amazon Chime Voice Connector\.

1. Choose **Phone numbers**\.

1. Select one or more phone numbers to unassign from the Amazon Chime Voice Connector\.

1. Select **Unassign**\.

1. Select the check box, and choose **Unassign**\.

## Deleting an Amazon Chime Voice Connector<a name="delete-voicecon"></a>

Before you can delete an Amazon Chime Voice Connector, you must unassign all phone numbers from it\. For more information on unassigning phone numbers from an Amazon Chime Voice Connector, see the previous topic\.

**To delete an Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Voice connectors**\.

1. Choose **Phone numbers**, **Delete voice connector**\.

1. Select the check box, and choose **Delete**\.