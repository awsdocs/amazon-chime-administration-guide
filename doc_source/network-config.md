# Network Configuration and Bandwidth Requirements<a name="network-config"></a>

Amazon Chime requires the following hosts, ports, and protocols to support various services\. If inbound or outbound traffic is blocked, this might affect the ability to use various services, including audio, video, screen sharing, or chat\. 

![\[Required hosts, ports, and protocols to support services\]](http://docs.aws.amazon.com/chime/latest/ag/images/hosts.PNG)

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