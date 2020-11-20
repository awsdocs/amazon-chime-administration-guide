# Creating a SIP application<a name="create-sip-app"></a>

You create a SIP application when you need to enable calling to and from a voice connector, voice connector group, or a private phone number\.

1. In the Amazon Chime console, in the navigation pane, choose **SIP media applications**\.

   The **Sip media application** page appears\.

1. Choose **Create**\.

   The **Create a SIP media application** appears\.

1. In the **Name** box, enter a name for your application\.

1. Open the **AWS Regions** list and select a region\. Make sure your selection matches the region in your Lambda's Amazon Resource Name \(ARN\)\. For example, if your ARN contains **us\-east\-1**, choose the list item with that same region\.

1. Copy your Lambda ARN and paste it into the **ARN** box\.

1. Choose **Create**\.

   A success message appears at the top of the SIP media applications page, and your media application appears in the list of apps\. If you see an error message, follow its instructions\.