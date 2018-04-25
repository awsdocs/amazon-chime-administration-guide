# Managing Your Amazon Chime Accounts<a name="manage-chime-account"></a>

If you are using Amazon Chime as an individual user or as a group with no administrators, and you want to expand your pilot or proof of concept to include administrator functionality or you want to buy Pro, you must create an Amazon Chime account in the AWS Management Console\. You can decide whether to create a **team account** or **enterprise account**\. 

A **team account** is the easiest way to start inviting users to your organization and grant them Pro permissions\. You only pay for users when they host meetings\. You don’t have to claim a domain, and you can invite users from any email domain that hasn't been claimed by another company\. Everyone in the same team account is able to search and locate other registered Amazon Chime users in the team\. A team account is also the right choice for paying for Pro users outside of your organization\.

An **enterprise account** provides more control over your users from your company domains, and includes the ability to connect to your Microsoft Active Directory for authentication and assign user permissions\. Enterprise accounts provide full management of users within your account, ensuring that all users that join Amazon Chime using your claimed domains are included in your centrally managed Amazon Chime account\. Enterprise administrators also can suspend and activate users\. Enterprise accounts require claiming at least one email domain\. They are best when you want to use the full administrative capabilities that Amazon Chime has to offer, including the ability to prevent specific users from signing in\. Enterprise accounts simplify the process of adding users and are required for the additional benefits of managing your users through Active Directory\. 

**Note**  
You can convert your team account to enterprise by claiming one or more email domains\. After your account is converted, the ability to connect an Active Directory instance through AWS Directory Service becomes available\. You can decide whether to continue to have your users sign in with Login with Amazon, or connect and authenticate via their Active Directory credentials\. If you don't connect to an Active Directory, your users sign in with Login with Amazon \(or an Amazon\.com account\)\. When Active Directory is set up, your users authenticate with their Active Directory credentials\.

**Topics**
+ [Create an Amazon Chime Account](invite-users-enterprise.md)
+ [Rename Your Account](suspend-users.md)
+ [Delete Your Account](enterprise-account.md)
+ [Use the Policies Page](policies.md)
+ [Claim a Domain](claim-domain.md)
+ [Connect to Your Active Directory](active_directory.md)