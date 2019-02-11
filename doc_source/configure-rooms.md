# Conference Room Configuration<a name="configure-rooms"></a>

Amazon Chime can integrate with your in\-room video hardware from Cisco, Tandberg, Polycom, Lifesize, Vidyo, or others when you use the SIP or H\.323 protocol\.

Conference room VTC devices that support SIP must dial "meet\.chime\.in" or "u@meet\.chime\.in" to connect to Amazon Chime\. Devices that only support H\.323 must dial 52\.23\.133\.56 or 52\.54\.206\.237\. In both cases, if a firewall is filtering traffic between the VTC device and Amazon Chime, open the ranges for the protocol\(s\) used\. For more information, see [Network Configuration and Bandwidth Requirements](network-config.md)\.

The following table is a subset of the compatible VTC devices list\.


| Device | SIP | H\.323 | Comment | 
| --- | --- | --- | --- | 
| Cisco SX20 | Yes | Yes | Audio/Video/Screen: To and From OK | 
| Cisco DX80 | Yes | Yes | Audio/Video/Screen: To and From OK | 
| Tandberg C40 | Yes | Yes | Audio/Video/Screen: To and From OK | 
| Polycom RealPresence Desktop | No | Yes | Audio/Video: OK, Screen: From device is OK | 
| Polycom Debut | No | Yes | Audio/Video: OK, Screen: From device is OK | 