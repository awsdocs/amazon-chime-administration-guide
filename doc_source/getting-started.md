# Getting Started<a name="getting-started"></a>

The easiest way for your users to get started with Amazon Chime is to download and use the Amazon Chime Pro version for free for 30 days\. For more information, see [Download Amazon Chime](https://aws.amazon.com/chime/trial)\.

**Purchasing Amazon Chime**  
To continue using the Amazon Chime Pro version after the 30 day free trial period, you must create an Amazon Chime administrator account and add your users to it\. To get started, you must first complete the [Prerequisites](prereqs.md), which include creating an AWS account\. Then, you can create and configure an Amazon Chime administrator account and add users to it by completing the following tasks\.

**Topics**
+ [Step 1: Creating an Amazon Chime Administrator Account](#create-account)
+ [Step 2 \(Optional\): Configuring Account Settings](#acct-settings)
+ [Step 3: Adding Users to Your Account](#add-users)

## Step 1: Creating an Amazon Chime Administrator Account<a name="create-account"></a>

After you complete the [Prerequisites](prereqs.md), you can create an Amazon Chime administrator account\.

**To create an Amazon Chime administrator account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, choose **New account**\.

1. For **Account Name**, enter a name for the account and choose **Create account**\.

## Step 2 \(Optional\): Configuring Account Settings<a name="acct-settings"></a>

By default, new accounts are created as **Team** accounts\. If you prefer to claim a domain and connect to your own identity provider, or Okta SSO, you can upgrade to an **Enterprise** account\. For more information about **Team** and **Enterprise** account types, see [Managing Your Amazon Chime Accounts](manage-chime-account.md)\.

**To upgrade to an **Enterprise** account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, choose the name of the account to upgrade\.

1. For **Identity**, choose **Getting Started**\.

1. Follow the steps in the console to claim your domain, set up your identity provider, and configure your directory group as needed\.

For more information about claiming domains, see [Claiming a Domain](claim-domain.md)\. For more information about setting up identity providers, see [Connecting to Your Active Directory](active_directory.md) and [Connecting to Okta SSO](okta_sso.md)\.

You can also allow or disallow account policies for options such as remote control of shared screens and the Amazon Chime call me feature\.

**To configure account policies**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, choose the name of the account to configure\.

1. For **Settings**, choose **Policies**\.

1. Select or clear the account policy options you want to allow or disallow\.

1. Choose **Change**\.

For more information, see [Using the Policies Page](policies.md)\.

## Step 3: Adding Users to Your Account<a name="add-users"></a>

After your Amazon Chime **Team** account is created, invite yourself and your users to join it\. If you are upgrading your account to an **Enterprise** account, you do not need to invite your users\. Instead, upgrade to an **Enterprise** account and claim your domain\. For more information, see [Step 2 \(Optional\): Configuring Account Settings](#acct-settings)\.

**To add users to your Amazon Chime account**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, choose the name of your account\.

1. On the **Users** page, choose **Invite users**\.

1. Enter the email addresses of the users to invite, including yourself, and choose **Invite users**\. 

The invited users receive email invitations to join the Amazon Chime team that you created\. When they register their Amazon Chime user accounts, they receive Pro permissions by default, and their 30\-day trial ends\. If they have already signed up for an Amazon Chime user account with their work email address, they can continue to use that account\. They can also download the Amazon Chime client app at any time by choosing **Download Amazon Chime** and signing in to their user account\.

You are only charged for a user with Pro permissions when they host a meeting\. There is no charge for users with Basic permissions\. Basic users cannot host meetings, but they can attend meetings and use chat\. For more information on pricing and the features that users with Pro and Basic permissions can access, see [Plans and pricing](https://aws.amazon.com/chime/pricing)\.

**To change user permissions**

1. Open the Amazon Chime console at [https://console\.chime\.aws\.amazon\.com/](https://console.chime.aws.amazon.com)\.

1. On the **Accounts** page, choose the name of your account\.

1. On the **Users** page, select the user or users to change permissions for\.

1. Choose **User actions**, **Assign user permission**\.

1. For **Permissions**, select **Pro** or **Basic**\.

1. Choose **Assign**\.

To provide other users with administrator permissions, while controlling their access to the Amazon Chime console for your account, see [Controlling Access to the Amazon Chime Console](control-access.md)\.