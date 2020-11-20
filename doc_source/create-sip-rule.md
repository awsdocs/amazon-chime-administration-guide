# Creating a SIP rule<a name="create-sip-rule"></a>

As a reminder, you need at least one private phone number – or a voice connector – and at least one SIP application before you can create a SIP rule\. You can use rules created by other administrators\.

**To create a SIP rule**

1. In the navigation pane, choose **SIP media applications**, copy the ID of the application for which you need to create a rule, then paste the ID into Notepad or a similar program\. Keep that program open for later use\. This allows you to copy and paste a phone number or ARN and still have the application ID available for use later in these steps\.

1. In the navigation pane, choose **SIP rules**\.

   The **SIP rules** page appears\.

1. Choose **Create**\.

   The **Create a SIP rule** dialog box appears\.

1. In the **Name** box, enter a name for the rule, then do one of the following:

   **Create a rule for a phone number**

   1. By default, the **Trigger type** list displays **To phone number**\. If it doesn't, open the list and select that value\.

   1. In the **Phone number** box, enter a phone number or choose one from the list\. If you enter a number, use this format: **\+1***ten\-digit number*\. For example: \+15095551212\.

   **Create a rule for a voice connector**

   1. Open the **Trigger type** list and choose **Request URI host name**\.

   1. Paste the ID that you copied in step 1 into the **Request URI host name** box\.

1. To use the rule immediately, leave the **Enabled** checkbox alone\. To disable the rule – until a voice connector comes online, for example – clear the checkbox\.

1. Choose **Next**, and on the **Step 2** page, paste – or copy and paste – the ID from step 1 into the **SIP media application** box\.

1. Choose **Create\.**

   A success message appears\. If an error message appears, follow its instructions\.