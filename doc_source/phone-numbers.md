# Managing phone numbers in Amazon Chime<a name="phone-numbers"></a>

Use the Amazon Chime console to provision phone numbers\. Choose from Amazon Chime Business Calling or Amazon Chime Voice Connector phone numbers\.

**Amazon Chime Business Calling**  
Lets your users send and receive phone calls and text messages directly from Amazon Chime\. Provision your phone numbers in the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com), or port in existing phone numbers\. Assign the phone numbers to your Amazon Chime users and grant them permissions to send and receive phone calls and text messages using Amazon Chime\.  
Business Calling does not support emergency calls\. It also doesn't support text messaging to and from short codes or short numbers\.

**Amazon Chime Voice Connector**  
Provides Session Initiation Protocol \(SIP\) trunking service for an existing phone system\. Port in existing phone numbers or provision new phone numbers in the Amazon Chime console\. Use the Amazon Chime Voice Connector phone numbers for inbound or outbound calling, or both\. For more information, see [Managing Amazon Chime Voice Connectors](voice-connectors.md)\.

**Note**  
Amazon Chime does not offer emergency calling services\. If you want to contact emergency calling services in the United States with Amazon Chime, you must obtain an emergency call routing number from a third\-party emergency service provider and provide it to Amazon Chime\. Third\-party emergency calls only work with Amazon Chime Voice Connectors\. Business Calling does not support emergency calls\. For more information, see [Setting up emergency call routing numbers for your Amazon Chime Voice Connector](chime-voice-connector-emergency-calling.md)\.

There are bandwidth requirements for using Amazon Chime Business Calling and integrating an Amazon Chime Voice Connector\. For more information, see [Bandwidth requirements](network-config.md#bandwidth)\.

**Topics**
+ [Provisioning phone numbers](provision-phone.md)
+ [Porting existing phone numbers](porting.md)
+ [Managing phone number inventory](phone-inventory.md)
+ [Updating outbound calling names](calling-name.md)
+ [Deleting phone numbers](delete-phone.md)
+ [Restoring deleted phone numbers](restore-phone.md)