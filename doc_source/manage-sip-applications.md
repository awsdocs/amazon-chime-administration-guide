# Managing SIP applications and rules<a name="manage-sip-applications"></a>

The topics in this section explain how to use the Amazon Chime administrative console to create Session Initiation Protocol \(SIP\) media applications and rules\. SIP media applications provide custom signaling and media instructions that you would normally build on your private branch telephone exchange \(PBX\)\. SIP rules associate each SIP application with a phone number or Amazon Chime Voice Connector\.

Amazon Chime runs the rules when a user places or receives a call\. Calls can go to and from an Amazon Chime Voice Connector or to and from private phone numbers that you own\.

You can save time with SIP media applications in part because they use AWS Lambdas, and you need at least one Lambda before you can create SIP applications\. SIP apps use Lambdas because:
+ You can write complex logic that involves decision making\. For example, a customer can use a touchtone phone to dial in to a meeting\. In turn, that number can trigger a lookup and route the caller to the correct meeting\.
+ Lambdas don't rely on servers for data provisioning, so they run faster, and you can deploy them with less work\.

  For general information about Lambdas, see [ AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/)\. For information about building Lambda's for use with SIP applications, see [ Building Lambdas for SIP media applications SDK ](https://docs.aws.amazon.com/chime/latest/dg/build-lambdas-for-sip-sdk.html)\. 

To create SIP rules, you need private phone numbers or at least one Amazon Chime Voice Connector\. For more information about phone numbers, see [ Managing phone numbers](https://docs.aws.amazon.com/chime/latest/ag/phone-numbers.html)\. For more information about Amazon Chime Voice Connectors, see [ Managing Amazon Chime Voice Connectors](https://docs.aws.amazon.com/chime/latest/ag/voice-connectors.html)\.

**Topics**
+ [Understanding the SIP data models](understand-sip-data-models.md)
+ [Using SIP applications](use-sip-apps.md)
+ [Using SIP rules](use-sip-rules.md)