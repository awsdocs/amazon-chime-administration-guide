# Understanding the SIP data models<a name="understand-sip-data-models"></a>

The Amazon Chime implementation of SIP media applications provides two data models: SIP media application and SIP rule\. You use the **SIP media applications** and **SIP rules** pages in the Amazon Chime console to create applications and rules\.

The following diagram shows how the data models work\. It shows how SIP rules can route calls from phone numbers and Request URI hostnames to different SIP applications\.

![\[Diagram of SIP media application and rule models.\]](http://docs.aws.amazon.com/chime/latest/ag/images/SIP-Data-Models.png)

The diagram illustrates the following:
+ The first row of the diagram shows that only a phone number or Request URI hostname can initiate a SIP media application\.
+ The first and second rows in the digram show that you can only associate a SIP rule with a single phone number or Request URI hostname\.
+ You can create many rules for a SIP media application, but you can only create one application per rule\. The second SIP application in the diagram shows how this can work\. It uses three rules, one set for a phone number and two set for Request URI hostnames\. 
+ As shown in the last row, a function can invoke one SIP media application, but multiple applications can invoke a single function\.