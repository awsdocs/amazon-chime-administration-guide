# Managing SIP media applications and rules<a name="manage-sip-applications"></a>

You can use the Amazon Chime console to create Session Initiation Protocol \(SIP\) media applications\. SIP media applications make it easier and faster for you to create custom signaling and media instructions that you would normally build on your private branch telephone exchange \(PBX\)\.

SIP rules specify how a SIP media application can connect to an Amazon Chime meeting\. Calls can go to and from private phone numbers that you own or to and from a Request URI hostname, the name assigned to an Amazon Chime Voice Connector\. Amazon Chime runs the SIP rules when a user places or receives a call\.

You must be an AWS Lambda user before you can create SIP media applications\. The SIP media applications use Lambda functions for the following reasons:
+ You can write complex logic that involves decision\-making\. For example, a caller can use a touchtone phone to dial in to a meeting\. In turn, that phone number triggers Lambda functions that ask for a meeting PIN and route the caller to the correct meeting\.
+ You can deploy Lambda functions without a server infrastructure\.

For more information about AWS Lambda, see [ Getting started with AWS Lambda](https://docs.aws.amazon.com/https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html)\.

To create SIP rules, you need private phone numbers or at least one Request URI hostname\. For more information about phone numbers, see [ Managing phone numbers](https://docs.aws.amazon.com/https://docs.aws.amazon.com/chime/latest/ag/phone-numbers.html)\. For more information about Request URI hostnames, see [Creating a SIP rule](create-sip-rule.md)\. 

**Topics**
+ [Understanding the SIP data models](understand-sip-data-models.md)
+ [Using SIP media applications](use-sip-apps.md)
+ [Using SIP rules](use-sip-rules.md)