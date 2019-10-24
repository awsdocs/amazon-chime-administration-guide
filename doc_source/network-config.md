# Network Configuration and Bandwidth Requirements<a name="network-config"></a>

Amazon Chime requires the destinations and ports described in this topic to support various services\. If inbound or outbound traffic is blocked, this blockage might affect the ability to use various services, including audio, video, screen sharing, or chat\.

Amazon Chime uses Amazon Elastic Compute Cloud \(Amazon EC2\) and other AWS services on port TCP/443\. If your firewall blocks port TCP/443, you must put `*.amazonaws.com` on an allow list, or put [AWS IP Address Ranges](https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html) in the *AWS General Reference* for the following services:
+ Amazon EC2
+ Amazon CloudFront
+ Amazon Route 53

**Note**  
Amazon Chime is in the process of simplifying its firewall requirements for audio, video, and screen sharing\. For more information, see [Amazon Chime Firewall Simplification](https://answers.chime.aws/articles/814/amazon-chime-firewall-simplification.html)\.

## Common<a name="common"></a>

The following destinations and ports are recommended when running Amazon Chime in your environment\.


| Destination | Ports | 
| --- | --- | 
|  chime\.aws  |  TCP/443  | 
|  \*\.chime\.aws  |  TCP/443  | 
|  \*\.amazonaws\.com  |  TCP/443  | 

Amazon Chime will start using the following destination and port soon\.


| Destination | Ports | 
| --- | --- | 
|  99\.77\.128\.0/18  |  TCP/443  | 

## Meetings and Business Calling<a name="meet-call"></a>

Amazon Chime will start using the following destination and port for meetings and Amazon Chime Business Calling soon\.


| Destination | Ports | 
| --- | --- | 
|  99\.77\.128\.0/18  |  UDP/3478  | 

Amazon Chime is in the process of retiring the following destinations and ports\.


| Destination | Ports | 
| --- | --- | 
|  52\.54\.62\.192/26  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 
|  52\.54\.63\.0/25  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 
|  52\.54\.63\.128/26  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 
|  52\.55\.63\.128/25  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 
|  34\.212\.67\.64/26  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 
|  34\.212\.95\.0/25  |  TCP/443 UDP/16384:17383 UDP/3478 UDP/7200  | 

## H\.323 Room Systems<a name="h323"></a>

Amazon Chime will start using the following destinations and ports for H\.323 in\-room video systems soon\.


| Destination | Ports | 
| --- | --- | 
|  13\.248\.147\.139  |  TCP/1720  | 
|  76\.223\.18\.152  |  TCP/1720  | 
|  99\.77\.128\.0/18  |  TCP/10000:60000 UDP/10000:60000  | 

Amazon Chime is in the process of retiring the following destinations and ports for H\.323\.


| Destination | Ports | 
| --- | --- | 
|  52\.23\.133\.56  |  TCP/1720  | 
|  52\.54\.206\.237  |  TCP/1720  | 
|  52\.55\.62\.128/25  |  TCP/1024:65535 UDP/1024:65535  | 
|  52\.55\.63\.0/25  |  TCP/1024:65535 UDP/1024:65535  | 

## Session Initiation Protocol \(SIP\) Room Systems<a name="sip"></a>

The following destinations and ports are recommended when running Amazon Chime for SIP in\-room video systems in your environment\.


| Destination | Ports | 
| --- | --- | 
|  meet\.chime\.in  |  TCP/5060:5061  | 

Amazon Chime will start using the following destinations and ports for SIP in\-room video systems soon\.


| Destination | Ports | 
| --- | --- | 
|  13\.248\.147\.139  |  TCP/5060:5061 UDP/5060  | 
|  76\.223\.18\.152  |  TCP/5060:5061 UDP/5060  | 
|  99\.77\.128\.0/18  |  UDP/10000:60000  | 

Amazon Chime is in the process of retiring the following destinations and ports for SIP\.


| Destination | Ports | 
| --- | --- | 
|  52\.55\.62\.128/25  |  UDP/10000:60000  | 
|  52\.55\.63\.0/25  |  UDP/10000:60000  | 

## Amazon Chime Voice Connector<a name="cvc"></a>

The following destinations and ports are recommended if you use Amazon Chime Voice Connector\.

### Signaling<a name="cvc-signaling"></a>


| AWS Region | Destination | Ports | 
| --- | --- | --- | 
| US East \(N\. Virginia\) |  3\.80\.16\.0/23  |  UDP/5060 TCP/5060 TCP/5061  | 
| US West \(Oregon\) |  99\.77\.253\.0/24  |  UDP/5060 TCP/5060 TCP/5061  | 

### Media<a name="cvc-media"></a>


| AWS Region | Destination | Ports | 
| --- | --- | --- | 
| US East \(N\. Virginia\) |  3\.80\.16\.0/23  |  UDP/5000:65000  | 
| US East \(N\. Virginia\) |  52\.55\.62\.128/25  |  UDP/1024:65535  | 
| US East \(N\. Virginia\) |  52\.55\.63\.0/25  |  UDP/1024:65535  | 
| US East \(N\. Virginia\) |  34\.212\.95\.128/25  |  UDP/1024:65535  | 
| US East \(N\. Virginia\) |  34\.223\.21\.0/25  |  UDP/1024:65535  | 
| US West \(Oregon\) |  99\.77\.253\.0/24  |  UDP/5000:65000  | 

## Bandwidth Requirements<a name="bandwidth"></a>

Amazon Chime has the following bandwidth requirements for the media that it provides:
+ Audio 
  + 1:1 call: 54 kbps up and down
  + Large call: no more than 32 kbps extra down for 50 callers
+ Video
  + 1:1 call: 650 kbps up and down
  + HD mode: 1400 kbps up and down
  + 3–4 people: 450 kbps up and \(N\-1\)\*400 kbps down
  + 5–16 people: 184 kbps up and \(N\-1\)\*134 kbps down
  + Up and down bandwidth adapts lower for network conditions
+ Screen
  + 1\.2 mbps up \(when presenting\) and down \(when viewing\) for high quality\. This adapts as low as 320 kbps based on network conditions\.
  + Remote control: 800 kbps fixed

Amazon Chime Business Calling and Amazon Chime Voice Connector have the following bandwidth requirements:
+ Audio
  + Call: \~90 kbps up and down\. This includes media payload and packet overhead\.