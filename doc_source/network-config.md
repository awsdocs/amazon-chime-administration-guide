# Network Configuration and Bandwidth Requirements<a name="network-config"></a>

Amazon Chime requires the following hosts, ports, and protocols to support various services\. If inbound or outbound traffic is blocked, this might affect the ability to use various services, including audio, video, screen sharing, or chat\. 

## Full Solution<a name="full"></a>

The following hosts, ports, and protocols are recommended when running the full Amazon Chime solution in your environment\. These recommendations apply to native clients, the web application, and in\-room conference systems\.

![\[Required hosts, ports, and protocols to support full Amazon Chime solution services.\]](http://docs.aws.amazon.com/chime/latest/ag/images/hosts_full.PNG)

## Web Application Only<a name="web-app"></a>

The following hosts, ports, and protocols are recommended if you use the Amazon Chime web application only in your environment\.

![\[Required hosts, ports, and protocols recommended if you use the web application only in your environment.\]](http://docs.aws.amazon.com/chime/latest/ag/images/hosts_web.PNG)

## H\.323 Only<a name="h323"></a>

The following ports and protocols are recommended if you use in\-room video systems only via H\.323 in your environment\.

![\[Required hosts, ports, and protocols recommended if you use in-room video systems only via H.323 in your environment.\]](http://docs.aws.amazon.com/chime/latest/ag/images/hosts_h323.PNG)

## SIP Only<a name="sip"></a>

The following ports and protocols are recommended if you use in\-room video systems only via SIP in your environment\.

![\[Required hosts, ports, and protocols recommended if you use in-room video systems only via SIP in your environment.\]](http://docs.aws.amazon.com/chime/latest/ag/images/hosts_sip.PNG)

## Amazon Chime Voice Connector<a name="cvc"></a>

The following ports and protocols are recommended if you use Amazon Chime Voice Connector\.

![\[Required hosts, ports, and protocols recommended if you use Amazon Chime Voice Connector.\]](http://docs.aws.amazon.com/chime/latest/ag/images/vc-image.png)

## Bandwidth Requirements<a name="bandwidth"></a>

Amazon Chime has the following bandwidth requirements for media services that it provides:
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
  + 1\.2 mbps up \(presenting\) and down \(viewing\) for high quality \(adapts as low as 320 kbps for network conditions\)
  + Remote control: 800 kbps fixed

Amazon Chime Business Calling and Amazon Chime Voice Connector have the following bandwidth requirements:
+ Audio
  + Call: \~90 kbps up and down \(including media payload and packet overhead\)