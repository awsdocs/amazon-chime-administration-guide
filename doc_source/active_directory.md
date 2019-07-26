# Connecting to Your Active Directory<a name="active_directory"></a>

**Benefits**

Using your Active Directory has the following benefits:
+ Amazon Chime users can sign in with their Active Directory credentials\.
+ Administrators can choose which credential security features to add, including password rotation, password complexity rules, and multi\-factor authentication\.
+ When users accounts are disabled in your Active Directory, their Amazon Chime accounts are automatically disabled\.
+ You can specify which Active Directory groups receive Pro permissions\.
  + Multiple groups can be configured to receive Basic or Pro permissions\.
  + Users must be a member of either group to sign into Amazon Chime\.
  + Users in both groups receive a Pro license\.

**Requirements**

Before you can add your Active Directory to Amazon Chime, you must complete the following requirements:
+ Make sure that you have appropriate IAM permissions to configure Domains, Active Directory, and Directory Groups\.
+ Set up a directory with AWS Directory Service that is configured in the US East \(N\. Virginia\) region\. For more information, see the [AWS Directory Service Administration Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/)\. Amazon Chime can connect using AD Connector or Microsoft AD\.
+ Set up an Amazon Chime enterprise account\. For more information, see [Claiming a Domain](claim-domain.md)\.

After you add a directory to Amazon Chime, users are prompted to log in with their directory credentials when they log in using an email address from one of the domains that you added to your Amazon Chime enterprise account\.

**To connect to your Active Directory**

1. Open the Amazon Chime console at [https://chime\.aws\.amazon\.com/](https://chime.aws.amazon.com)\.

1. In the navigation pane, choose **Settings**, **Active directory**\.

1. For **Cloud directory ID**, select the AWS Directory Service directory to use for Amazon Chime, and then choose **Connect**\.
**Note**  
You can find your directory ID using the [AWS Directory Service console](https://console.aws.amazon.com/directoryservice/)\.

1. After your directory has been connected, choose **Add a new group**\. 

1. For **Group**, type a name for the group\. The name must exactly match an Active Directory group in the target directory\. Active Directory Organization Units \(OUs\) are not supported\.

1. For **Permission tier**, choose **Basic** or **Pro**\. 

1. Choose **Add Group**\.

1. Repeat this procedure to create additional directory groups\.

## Configuring Multiple Email Addresses<a name="multi-email"></a>

After you connect to your Active Directory, users that authenticate with Active Directory can use multiple email addresses\. They can use any of their work email addresses with Amazon Chime, as long as the email address is using a domain that has been claimed by your Amazon Chime account, and is associated with their user in Active Directory\. 

Amazon Chime continues to use the single email address in the EmailAddress attribute in Active Directory as the user’s primary email address\. This is the only one you can see in the interface\. Users can use any additional addresses in the ProxyAddress attribute, as long as the domain is claimed for the account\.

### Incorrect Configuration Example<a name="incorrect-config"></a>

Username shirley\.rodriguez is a member of an Amazon Chime account that has claimed two domains: example\.com and anotherdomain\.com\. In Active Directory, she has the following three email addresses \(one primary and two proxy\):
+ Primary email address: shirley\.rodriguez@example\.com
+ Proxy email address 1: shirley\.rodriguez@example2\.com
+ Proxy email address 2: srodriguez@anotherdomain\.com

This user can sign into Amazon Chime using shirley\.rodriguez@example\.com or srodriguez@anotherdomain\.com and her username shirley\.rodriguez\. If she attempts to sign in using shirley\.rodriguez@example2\.com, she is asked to **Log in with Amazon** and is not part of your managed account\. This is why it's important to claim all of the domains your users use for email\.

Other Amazon Chime users can add her as a contact, invite her to meetings, or add her as a delegate using either her shirley\.rodriguez@example\.com or srodriguez@anotherdomain\.com email address\. 

### Correct Configuration Example<a name="correct-config"></a>

Username shirley\.rodriguez is a member of an Amazon Chime account that has claimed three domains: example\.com, example2\.com, and anotherdomain\.com\. In Active Directory, she has the following three email addresses:
+ Primary email address: shirley\.rodriguez@example\.com
+ Proxy email address 1: shirley\.rodriguez@example2\.com
+ Proxy email address 2: srodriguez@anotherdomain\.com

This user can sign into Amazon Chime using any of her work email addresses\. Other users can also add her as a contact, invite her to meetings, or add her as a delegate using any of her work email addresses\. 