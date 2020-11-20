# Understanding the SIP data models<a name="understand-sip-data-models"></a>

The Amazon Chime SIP implementation provides two data models – SIP Application and SIP Rule\. You use the **SIP applications** and **SIP rules** pages in the administrative console to create applications and rules\.

This diagram shows how the data models work:

![\[The SIP application and rule models.\]](http://docs.aws.amazon.com/chime/latest/ag/images/sip-data-models.png)

In these models:
+ Only phone numbers and voice connectors can trigger your SIP applications\.
+ You can only associate a SIP rule with a single phone number or voice connector\.
+ Applications can have many rules, but a rule can only have one application\.
+ A Lambda function can invoke one application, but multiple applications can invoke a given Lambda function\.