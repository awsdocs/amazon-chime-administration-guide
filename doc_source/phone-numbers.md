# Working with Phone Numbers<a name="phone-numbers"></a>

Use the Amazon Chime console to provision phone numbers\. Choose from Amazon Chime Business Calling or Amazon Chime Voice Connector phone numbers\.

Amazon Chime Business Calling lets you provision and assign phone numbers to your existing Amazon Chime users\. You can grant your users permissions to send and receive phone calls and text messages using Amazon Chime\.

You can integrate an Amazon Chime Voice Connector with an existing phone system\. You can also use the Amazon Chime console to provision phone numbers for your Amazon Chime Voice Connector\. For more information, see [Working with Amazon Chime Voice Connectors](voice-connectors.md)\.

For information about bandwidth requirements for Amazon Chime Business Calling and Amazon Chime Voice Connector, see [Bandwidth Requirements](network-config.md#bandwidth)\.

Your phone number **Inventory** is limited to 25 phone numbers by default\.

## Provisioning Phone Numbers<a name="provision-phone"></a>

Use the Amazon Chime console to provision phone numbers for your Amazon Chime account\. Choose from the Amazon Chime Business Calling or Amazon Chime Voice Connector options\.

**To provision phone numbers**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Orders**, **Provision phone numbers**\.

1. Select **Business Calling** or **Voice Connector**, and choose **Next**\.

1. Search for available phone numbers by country and other location options\. Select the phone number or numbers to provision, then choose **Provision**\.

The phone numbers appear in your **Orders** and **Pending** lists\. When provisioning is complete, the phone numbers appear in your **Inventory** and can be assigned to individual users or Amazon Chime Voice Connectors that you create\.

Before you can assign provisioned phone numbers to an Amazon Chime Voice Connector, you must create the Amazon Chime Voice Connector\. For more information, see [Creating an Amazon Chime Voice Connector](voice-connectors.md#create-voicecon)\.

## Porting Existing Phone Numbers<a name="porting"></a>

You can port existing United States phone numbers from your phone carrier to use with Amazon Chime Business Calling or Amazon Chime Voice Connectors\. To port existing phone numbers to Amazon Chime, submit a support request from the Amazon Chime console\. The porting process can take between 2\-4 weeks\.

**Note**  
Toll\-free numbers can be ported for use with Amazon Chime Voice Connectors\. Toll\-free numbers are not currently supported for Amazon Chime Business Calling\.

**To port existing phone numbers**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. Choose **Support**, **Submit request**\.

1. For **Category**, choose **Other**\.

1. For **Subject**, enter **Porting phone numbers**\.

1. For **Issue**, enter the existing phone numbers to port\. Indicate the phone number type \(**Business Calling** or **Voice Connector**\)\.

1. For **Email**, enter the email address associated with your Amazon Chime administrator account\.

1. Choose **Submit request**\.

AWS Support responds to your support request to let you know whether your phone numbers can be ported from your existing phone carrier\. If your phone numbers can be ported, you are asked to complete a Letter of Authorization/Agency \(LOA\)\. This authorizes your phone carrier to release your existing phone numbers for porting\. Then, your phone numbers are ported to the phone carrier for Amazon Chime\.

The information provided on the LOA must match the information that your phone carrier has on file\. Mismatched information can delay the porting process\. If you are porting phone numbers from different carriers, fill out a separate LOA for each carrier\.

When the porting process is complete, the ported phone numbers appear in your **Inventory** and can be assigned to individual users or the Amazon Chime Voice Connectors that you create \.

## Managing Phone Number Inventory<a name="phone-inventory"></a>

Use the phone number management **Inventory** page to assign or unassign Amazon Chime Business Calling phone numbers for individual users, or Amazon Chime Voice Connector phone numbers for Amazon Chime Voice Connectors\.

Amazon Chime Business Calling phone numbers can also be managed within user profiles, and Amazon Chime Voice Connector phone numbers can be managed on the corresponding **Voice Connector** page\. For more information, see [Managing User Phone Numbers](user-phone.md) and [Assigning and Unassigning Amazon Chime Voice Connector Phone Numbers](voice-connectors.md#assign-voicecon)\.

**To assign an Amazon Chime Business Calling phone number to a user**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the Amazon Chime Business Calling phone number to assign to a user\.

1. Choose **Assign**\.

1. Select the account that the user belongs to, and choose **Next**\.

1. Select the user's full name, and choose **Assign**\.

For instructions on how to edit the user's calling and SMS permissions, see [Editing Calling and SMS Permissions](user-phone.md#edit-phone-perms)\. When you change a user's Amazon Chime Business Calling phone number or phone number permissions, we recommend contacting the user with their new phone number or permissions information\. Users must also sign out of their Amazon Chime account and sign back in again before they can access their new phone number or permissions features\.

**To assign Amazon Chime Voice Connector phone numbers to an Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the Amazon Chime Voice Connector phone number or numbers to assign to the Amazon Chime Voice Connector\.

1. Choose **Assign**\.

1. Select the Amazon Chime Voice Connector to assign the phone number to, and choose **Assign**\.

The following procedure unassigns phone numbers from individual users or Amazon Chime Voice Connectors\. 

**To unassign inventory phone numbers**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone number to unassign\.

1. Choose **Unassign**\.

1. Select the check box, and choose **Unassign**\.

View details about your inventory phone numbers to see which user or Amazon Chime Voice Connector a number is assigned to\. You can also see if phone calls and text messages are enabled\.

**To view inventory phone number details**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone number to view details for\.

1. For **Actions**, choose **View details**\.

If you have unassigned Amazon Chime Business Calling and Amazon Chime Voice Connector phone numbers, you can switch them from one product type to another\.

**To edit product types**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone number or numbers to change product types for\.

1. Select **Business Calling** or **Voice Connector**, and choose **Save**\.

## Deleting Phone Numbers<a name="delete-phone"></a>

Delete unassigned phone numbers from your phone number management **Inventory**\. For more information about unassigning phone numbers, see [Managing Phone Number Inventory](#phone-inventory)\.

**To delete unassigned phone numbers**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone number or numbers to delete\.

1. For **Actions**, choose **Delete phone number\(s\)**\.

1. Select the check box, and choose **Delete**\.

Deleted phone numbers are held in the **Deletion queue** for 7 days before they are deleted permanently\.

## Restoring Deleted Phone Numbers<a name="restore-phone"></a>

You can restore deleted phone numbers from the **Deletion queue** for up to 7 days after they are deleted\. Restoring a phone number moves it back into your **Inventory**\.

**To restore deleted phone numbers**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. For **Telephony**, choose **Phone number management**\.

1. Choose **Deletion queue**, and select the phone number or numbers to restore\.

1. Choose **Move to inventory**\.