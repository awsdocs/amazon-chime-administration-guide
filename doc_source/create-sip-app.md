# Creating a SIP media application<a name="create-sip-app"></a>

Create a SIP media application when you need to enable calling to and from a Request URI hostname, Amazon Chime Voice Connector group, or a private phone number\. 

**To create a SIP media application**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. In the Amazon Chime console, in the navigation pane, choose **SIP media applications**\.

   The **SIP media application** page appears\.

1. Choose **Create**\.

   The **Create a SIP media application** page appears\.

1. For **Name**, enter a name for your application\.

1. For **AWS Regions**, select a Region\. Make sure your selection matches the Region in your Lambda function's Amazon Resource Name \(ARN\)\. For example, if your function's ARN contains **us\-east\-1**, choose the list item with that same Region\.

1. Copy your Lambda function's ARN and paste it into the **ARN** box\.

1. Choose **Create**\.

   A success message appears at the top of the **Create a SIP media application** page, and your media application appears in the list of applications\. If you see an error message, follow its instructions\.