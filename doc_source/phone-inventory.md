# Managing phone number inventory<a name="phone-inventory"></a>

Use the phone number management **Inventory** page to assign or unassign phone numbers\. You can do this with Amazon Chime Business Calling phone numbers for individual users, or phone numbers for Amazon Chime Voice Connectors or Amazon Chime Voice Connector groups\.

Manage Amazon Chime Business Calling phone numbers from within user profiles\. Manage Amazon Chime Voice Connector phone numbers on the corresponding **Voice connectors** or **Voice connector groups** page\. For more information, see [Managing user phone numbers](user-phone.md), [Assigning and unassigning Amazon Chime Voice Connector phone numbers](assign-voicecon.md), or [Assigning and unassigning phone numbers for an Amazon Chime Voice Connector group](voice-connector-groups.md#assign-voicecon-group)\.

**To assign an Amazon Chime Business Calling phone number to a user**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Phone number management**\.

1. Choose **Inventory**, and select the Amazon Chime Business Calling phone number to assign to a user\.

1. Choose **Assign**\.

1. Select the account that the user belongs to, and choose **Next**\.

1. Select the user's full name, and choose **Assign**\.

For instructions on how to edit the user's calling and SMS permissions, see [Editing calling and SMS permissions](user-phone.md#edit-phone-perms)\. When you change a user's Amazon Chime Business Calling phone number or phone number permissions, we recommend providing the user with their new phone number or permissions information\. Before users can access their new phone number or permissions features, they must sign out of their Amazon Chime account and sign in again\.

**To assign Amazon Chime Voice Connector phone numbers to an Amazon Chime Voice Connector or Amazon Chime Voice Connector group**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone numbers that you want to assign\.

1. For **Assignment type**, choose **Voice connector** or **Voice connector group**\.

1. Choose **Assign**\.

1. Select the Amazon Chime Voice Connector to assign the phone number to, and choose **Assign**\.

You can also choose **Reassign** to reassign phone numbers with the **Voice Connector** product type\. This lets you reassign these numbers from one Amazon Chime Voice Connector or Amazon Chime Voice Connector group to another\.

**To assign an Amazon Chime SIP Media Application Dial\-In phone number to a SIP Media Application**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. In the navigation pane, choose **SIP media applications**, locate the SIP application for which you want to create a rule, then copy its phone number\. Paste the number into Notepad or a similar program\. Keep that program open for later use\. This keeps the number available for use later in these steps\.

1. In the navigation pane, choose **SIP rules**\. The **SIP rules** page appears\.

1. Choose **Create**\. The **Create a SIP rule** dialog box appears\.

1. For **Name**, enter a name for the rule, then create the rule:
   + By default, the **Trigger type** list displays **To phone number**\. If it doesn't, open the list and select that value\.
   + For **Phone number**, enter a phone number or choose one from the list\. If you enter a number, use this format: **\+1***ten\-digit number*\. For example: \+15095551212\.

1. To use the rule immediately, leave the **Enabled** check box selected\. To disable the rule, clear the check box\.

1. Choose **Next**, and on the **Step 2** page, open the **SIP media application** list and select the SIP application that you want to use\.

1. As needed, choose **Add a SIP media application** to use the rule with multiple applications, then choose **Create**\.

A success message appears\. If an error message appears, follow its instructions\.

The following procedure unassigns phone numbers from Amazon Chime Business Calling users or Amazon Chime Voice Connectors\. 

**To unassign inventory phone numbers for Amazon Chime Business Calling or Amazon Chime Voice Connector**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Phone number management**\.

1. Choose I**nventory**, and select the phone number to unassign\.

1. Choose **Unassign**\.

1. Select the check box, and choose **Unassign**\.

**To unassign inventory phone numbers for SIP Media Application**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. In the navigation pane, choose **SIP rules**\. The **SIP rules** page appears\. 

1. Choose the option button next to the name of the rule that you want to unassign\. 

1. Open the **Actions** list and choose **Delete**\. The **Delete rule\(s\)** dialog box appears\. 

1. Select **I understand that this action cannot be reversed**, then choose **Delete**\. 

You can also view the details of your inventory phone numbers\. For example, you can see which Amazon Chime Business Calling user, Voice Connector, or Amazon Chime SIP Media Application that a number is assigned to\. You can also see if phone calls and text messages are enabled\.

**To view inventory phone number details**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Phone number management**\. 

1. Choose **Inventory**, and select the phone number that you want to view\. 

1. For **Actions**, choose **View details**\.

If you have unassigned Amazon Chime Business Calling, Amazon Chime Voice Connector, or Amazon Chime SIP media application phone numbers, you can switch them from one product type to another\.

**Note**  
For non\-US numbers, you must use the SIP Media Application Dial\-In product type\.

**To edit product types**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. For **Calling**, choose **Phone number management**\.

1. Choose **Inventory**, and select the phone number or numbers that you want to change\. 

1. Select **Business Calling**, **Voice Connector**, or **SIP Media Application Dial\-In** and choose **Save**\. 