# Features {#concept_ejm_bhs_j2b .concept}

Smart Access Gateway provides devices of two models. The following table describes the differences in functionality between the device models:

|Feature|Functions|Description|SAG-100WM|SAG-1000|Related documents|
|-------|---------|-----------|---------|--------|-----------------|
|Basic connectivity|Static IP address for port|Configure a static IP address for the port.|√|√| [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 [SAG-1000 configuration guide](../../../../reseller.en-US/SAG-1000 Configuration Guide/Configuration guide.md#)

 |
|PPPoE connections through WAN port|Access the Internet through broadband \(dial-up mode\).|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 |
|4G support|Access the Internet by using a 4G connection.|√ Built-in LTE

 |√ External LTE

 | [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 [Configuration guide](../../../../reseller.en-US/SAG-1000 Configuration Guide/Configuration guide.md#)

 |
|LAN port DHCP|A newly established site automatically obtains the IP address.|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 |
|WIFI access|Access the Internet through Wi-Fi.|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 |
|Static routing|Existing on-premises networks are connected through static routing.|√|√| [SAG-100WM configuration guide](../../../../reseller.en-US/SAG-100WM Configuration Guide/Configuration guide.md#)

 [SAG-1000 configuration guide](../../../../reseller.en-US/SAG-1000 Configuration Guide/Configuration guide.md#)

 |
|OSPF|Support OSPF protocol.|×|√| [SAG-1000 web configuration](../../../../reseller.en-US/User Guide/Configure a Smart Access Gateway device/Web configurations for SAG-1000 devices.md#)

 |
|Internet SNAT|Access the Internet through the inline networking mode.|√|×| [SAG-100WM inline configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

 |
|Cross-region access to VPC|Access from one point to connect target VPCs around the globe through the intranet.|√|√| [Cross-border access to VPC](../../../../reseller.en-US/Best Practices/Cross-region access to VPC.md#)

 |
|Access control|Allow or forbid IP addresses in access control list \(ACL\) rules to access the Internet or intranet.|√|√|[Configure an access control list](../../../../reseller.en-US/User Guide/Access control list/Configure an access control list.md#)|
|Configuration|ZTP \(Zero Touch Provisioning\)|Zero-configuration deployment.|√|×| -

 |
|Networking mode|Inline mode|A newly established site uses Smart Access Gateway as the egress by which to access Alibaba Cloud.|√|×| [SAG-100WM inline configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

 |
|One-arm mode|An existing site accesses Alibaba Cloud through SAG without changing the existing network architecture.|×|√| [SAG-1000 dual-device one-arm mode configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-1000 dual-device one-arm dynamic-routing hot-backup configuration tutorial/Configuration overview.md#)

 |
|High availability|Physical connection backup|Add SAG as the backup link of an existing physical connection.|×|√| -

 |
|Dual-link backup-WAN + 4G|An SAG instance uses dual links formed by broadband and 4G to access the Internet.|√|Coming soon| [Link-level high availability configurations](../../../../reseller.en-US/User Guide/Smart Access Gateway/Link-level high availability configurations.md#)

 |
|Dual-device cold backup|The two devices share the bandwidth and operate in active/standby mode. This means if the active device fails, traffic is immediately directed to the standby device.|√|×| [Device-level high availability configurations](../../../../reseller.en-US/User Guide/Smart Access Gateway/Device-level high availability configurations.md#)

 |
|Dual-device hot backup|The two devices share the bandwidth and are online at the same time. Automatic detection and automatic switching are performed.|×|√| [Device-level high availability configurations](../../../../reseller.en-US/User Guide/Smart Access Gateway/Device-level high availability configurations.md#)

 |
|ECC + In|The two devices share the bandwidth and are online at the same time. Automatic detection and automatic switching are performed.|×|√| [Device-level high availability configurations](../../../../reseller.en-US/User Guide/Smart Access Gateway/Device-level high availability configurations.md#)

 |
|Security|VPN encryption|The connection is encrypted.|√|√| -

 |
|Access control|Intranet ACL management.|√|√| -

 |
|Offline device locking|Anti-theft, offline locking.|√|√| [Lock an offline device](../../../../reseller.en-US/User Guide/Smart Access Gateway/Lock an offline device.md#)

 |
|Operation and maintenance|Remote reboot|Reboot the device on the console.|√|√| [Reboot through the console](../../../../reseller.en-US/User Guide/Smart Access Gateway/Reboot through the console.md#)

 |
|Remote software upgrading|Upgrade the software version on the console.|√|√| [Upgrade the software version](../../../../reseller.en-US/User Guide/Smart Access Gateway/Upgrade the software version.md#)

 |
|Query the traffic|Query used traffic.|√|√| [Monitor traffic](../../../../reseller.en-US/Troubleshooting/Alarm management/Monitor traffic.md#)

 |
|Monitoring|Device level monitoring|Send notifications if both the active and standby IPsec links of an SAG device fail.|√|√| [Create an event alert](../../../../reseller.en-US/Troubleshooting/Alarm management/Create an event alert.md#)

 |
|Link level monitoring|Send notifications when the device is online.|√|√| [Create an event alert](../../../../reseller.en-US/Troubleshooting/Alarm management/Create an event alert.md#)

 |

