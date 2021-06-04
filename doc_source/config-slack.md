# Setting up the Amazon Chime Meetings App for Slack<a name="config-slack"></a>

If you use [ Slack Enterprise Grid Organizations ](https://slack.com/help/articles/360000281563-Manage-apps-on-Enterprise-Grid), and you own or administer a Slack organization, you can set up the Amazon Chime Meetings App for Slack for your organizations\. If you're a Slack workspace administrator, you can set up the Amazon Chime Meetings App for Slack for your workspaces\.

The steps in the following sections explain how to perform both types of setups, and how to complete additional tasks such as migrating a workspace to an organization\.

**Topics**
+ [Installing the Amazon Chime Meetings App for Slack on an organization](#install-org)
+ [Installing the Amazon Chime Meetings App for Slack on workspaces](#install-workspace)
+ [Migrating workspaces to organizations](#migrate-workspace)
+ [Associating workspaces with Amazon Chime Team accounts](#associate-with-team-acct)

## Installing the Amazon Chime Meetings App for Slack on an organization<a name="install-org"></a>

Installing the Amazon Chime Meetings App for Slack on a Slack organization enables users to start instant meetings and calls with other users in the various workspaces in that organization\. It also enables workspace administrators to install the Amazon Chime Meetings App for Slack meetings application automatically on any new workspaces\. The following steps explain how\.

**Note**  
The following steps assume that you are an organization owner or administrator, and that you can log in to the Slack management console\.

**To set up the Amazon Chime Meetings App for Slack on an organization**

1. In the left\-hand pane of the Slack management console, choose **Apps**\.

   The **Apps** page appears and lists the organization's installed apps, if any\.

1. Choose **Manage Apps**, located in the upper\-right corner of the page, then choose **Install an app**\.

   The **Find an app to install** dialog box appears\.

1. Search on **Amazon Chime Meetings**, then select it in the search results\.

   The **Add Amazon Chime Meetings to workspaces** dialog box appears and lists the workspaces in the organization\.

1. Choose the workspace or workspaces on which you want to install Amazon Chime Meetings App for Slack\.

1. Optionally, choose **Default for future workspace** if you want to automatically install the Amazon Chime Meetings App for Slack in all new workspaces, then choose **Next**\.

   The **Review this app’s requested permissions** dialog box appears and displays the permissions and actions for the Amazon Chime Meetings App for Slack\.

1. Choose **Next**\.

1. If you chose to install the Amazon Chime Meetings App for Slack on new workspaces by default, choose **I’m ready to set this app as a default for future workspaces**, and then choose **Save**\. Otherwise, just choose **Save**\.

**Note**  
You can also use OAuth to install apps in your organizations\. For more information, see [ Installing with OAuth ](https://api.slack.com/authentication/oauth-v2) in the Slack help\.

## Installing the Amazon Chime Meetings App for Slack on workspaces<a name="install-workspace"></a>

Installing the Amazon Chime Meetings App for Slack on a workspace enables users to start instant meetings and calls with other users in that workspace\. Users don't need an Amazon Chime user profile to use the Amazon Chime Meetings App for Slack\. They can log in with their Slack user profiles and start calls or meetings at any time\. If users need to conduct meetings with more than one other person, you must setup an Amazon Chime Team account and grant those additional users Pro permissions\. For more information about starting Amazon Chime calls and meetings, see [Using the Amazon Chime Meetings App for Slack](https://docs.aws.amazon.com/chime/latest/ug/using-slack.html) in the *Amazon Chime User Guide*\. For more information about setting up an Amazon Chime Team account, see [Associating workspaces with Amazon Chime Team accounts](#associate-with-team-acct) in this guide\. 

**To install the Amazon Chime Meetings App for Slack for Slack workspaces**

1. Navigate to the Slack App Directory and locate the Amazon Chime Meetings App\.

1. Choose [ **Add to Slack**](https://signin.id.ue1.app.chime.aws/auth/slack?purpose=app_authz) to install the Amazon Chime Meetings App for Slack from the Slack App Directory\.

1. Configure your Slack workspace **Calls** setting to **Enable calling in Slack, using Amazon Chime**\.

## Migrating workspaces to organizations<a name="migrate-workspace"></a>

If you own a Slack organization, you can migrate workspaces into that organization\. For more information about migrating workspaces, see [ Migrate workspaces to Enterprise Grid](https://slack.com/help/articles/115002532808-Migrate-workspaces-to-Enterprise-Grid) in the Slack help\.

## Associating workspaces with Amazon Chime Team accounts<a name="associate-with-team-acct"></a>

Associate your workspace with an Amazon Chime Team account to manage your users' permissions\. You can upgrade meeting hosts to Amazon Chime Pro so that they can start meetings with up to 250 attendees and 16 video tiles, and include phone numbers to dial in for audio\. Assign users Amazon Chime Basic permissions so they can start one\-on\-one meetings or join Amazon Chime meetings\. For more information, see [Amazon Chime Pricing](http://aws.amazon.com/chime/pricing/)\.

**Note**  
If you associate an Amazon Chime Team account with your Slack workspace, users can sign in to Amazon Chime from the Amazon Chime Meetings App for Slack\. You can change this setting at any time\. For more information, see [Managing meeting settings](mtg-settings.md)\.

Before you can associate your Slack workspace with an Amazon Chime Team account, you must create an AWS account\. For more information about how to create an AWS account, see [Prerequisites](prereqs.md)\.

**To associate your Slack workspace with an Amazon Chime Team account when installing the Amazon Chime Meetings App for Slack**

1. Immediately after installing the Amazon Chime Meetings App for Slack in your Slack workspace, choose **Upgrade now**\.

1. Follow the prompts to sign in to the Amazon Chime console using your AWS account credentials\.

1. Follow the prompts to create a new Team account in Amazon Chime or choose an existing one\.
   + **Create a new account** – Create a new Amazon Chime account to which to invite your Slack users\. Enter an account name, choose whether to invite your Slack users, then choose **Create**\.
   + **Choose an existing account** – Select an existing Amazon Chime account to invite your Slack users to\. Select the account, then choose **Invite**\.

When you invite your Slack users to join Amazon Chime, they receive an email invitation\. When they accept the invitation, they are automatically upgraded to Amazon Chime Pro\.

If you did not associate your Slack workspace with an Amazon Chime Team account when you installed the Amazon Chime Meetings App for Slack, you can do so after the fact by using the following steps\.

**To associate your Slack workspace with an Amazon Chime Team account after installing the Amazon Chime Meetings App for Slack**

1. Sign in to your AWS account\.

1. Sign in to your Slack workspace as an administrator\.

1. Go to [ https://signin\.id\.ue1\.app\.chime\.aws/auth/slack?purpose=app\_authz](https://signin.id.ue1.app.chime.aws/auth/slack?purpose=app_authz)\.

1. Follow the prompts to create a new Team account in Amazon Chime or choose an existing account\.
   + **Create a new account** – Create a new Amazon Chime account to which to invite your Slack users\. Enter an account name, choose whether to invite your Slack users, then choose **Create**\.
   + **Choose an existing account** – Select an existing Amazon Chime account to invite your Slack users to\. Select the account, then choose **Invite**\.