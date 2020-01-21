# Porting Existing Phone Numbers<a name="porting"></a>

You can port existing United States phone numbers from your phone carrier to use with Amazon Chime Business Calling or Amazon Chime Voice Connectors\. To do so, submit a support request from the Amazon Chime console\. The porting process can take between 2\-4 weeks\.

Before you can port phone numbers for Amazon Chime Voice Connectors, you must create an Amazon Chime Voice Connector\. For more information, see [Creating an Amazon Chime Voice Connector](create-voicecon.md)\.

**Note**  
You can port toll\-free numbers for Amazon Chime Voice Connectors\. Toll\-free numbers are not currently supported for Amazon Chime Business Calling\.

## Porting Phone Numbers into Amazon Chime<a name="port-in"></a>

**To port existing phone numbers into Amazon Chime**

1. Do one of the following:
   + Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

     Choose **Support**, **Submit request**\.
   + If you are an AWS Premium Support customer, open the [AWS Support Center](https://console.aws.amazon.com/support/home#/) page, sign in if necessary, and choose **Create case**\.

1. For **Category**, choose **Other**\.

1. For **Subject**, enter **Porting phone numbers in**\.

1. For **Issue**, enter the following:
   + Existing phone numbers to port in\. Indicate the phone number type, **Business Calling** or **Voice Connector**\.
   + Billing Telephone Number \(BTN\) of the account\.
   + Authorizing person’s name\. This is the person in charge of account billing with the current carrier\.
   + Current carrier, if known\.
   + Service account number, if this information is present with the current carrier\.
   + Service PIN, if available\.
   + Service address and customer name, as they appear in your current carrier contract\.
   + Requested date and time for the port\.
   + \(Optional\) If you are porting your BTN, indicate one of the following options:
     + **I am porting my BTN and I want to replace it with a new BTN that I am providing\. I can confirm that this new BTN is on the same account with the current carrier\.**
     + **I am porting my BTN and I want to close out my account with my current carrier\.**
     + **I am porting my BTN because my account is currently set up so that each phone number is its own BTN\.** \(Select this option only when your account with the current carrier is set up this way\.\)

1. For **Email**, enter the email address associated with your Amazon Chime administrator account\.

1. Choose **Submit request**\.

1. AWS Support responds to your support request to let you know whether your phone numbers can be ported from your existing phone carrier\.

1. If your phone numbers can be ported, AWS Support asks you to complete a Letter of Authorization/Agency \(LOA\)\. This authorizes your existing phone carrier to release your existing phone numbers for porting\.

1. \(Optional\) If you are porting phone numbers from different carriers, complete a separate LOA for each carrier\.

1. After you submit the LOA, AWS Support works with your existing phone carrier to confirm that the information on the LOA is correct\. If the information provided on the LOA does not match the information that your phone carrier has on file, AWS Support contacts you to update the information provided on the LOA\.

1. After your existing phone carrier confirms that the LOA is correct, they review and approve the requested port\. Then they provide AWS Support with a Firm Order Commit \(FOC\) date and time for the port to occur\.

1. AWS Support contacts you with the FOC to confirm that the date and time works for you\.

1. One day before the FOC date, the ported phone numbers appear in the Amazon Chime console under your **Phone number management Inventory**\. You can then assign the ported phone numbers to individual users as Amazon Chime Business Calling phone numbers, or assign the phone numbers to Amazon Chime Voice Connectors that you create\. For more information, see [Managing Phone Number Inventory](phone-inventory.md) and [Creating an Amazon Chime Voice Connector](create-voicecon.md)\.

1. On the FOC date, the ported phone numbers are activated for use with Amazon Chime\.

## Porting Phone Numbers out of Amazon Chime<a name="port-out"></a>

**To port existing phone numbers out of Amazon Chime**

1. Do one of the following:
   + Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

     Choose **Support**, **Submit request**\.
   + If you are an AWS Premium Support customer, open the [AWS Support Center](https://console.aws.amazon.com/support/home#/) page, sign in if necessary, and choose **Create case**\.

1. For **Category**, choose **Other**\.

1. For **Subject**, enter **Porting phone numbers out**\.

1. For **Issue**, enter the phone numbers to port out\. Indicate the phone number type, **Business Calling** or **Voice Connector**\.

1. For **Email**, enter the email address associated with your Amazon Chime administrator account\.

1. Choose **Submit request**\.

AWS Support responds with an account ID and PIN to use when requesting the port from your new carrier\.

When the porting process is complete and the phone numbers are ported to your new carrier, unassign and delete the phone numbers from your Amazon Chime inventory\. For more information, see [Managing Phone Number Inventory](phone-inventory.md) and [Deleting Phone Numbers](delete-phone.md)\.