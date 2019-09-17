# SAG functions {#concept_ejm_bhs_j2b .concept}

This topic describes the features and functions of SAG-100WM and SAG-1000. \(The symbol '√' indicates 'supported', while '×' indicates 'not supported'\).

|Feature|Function|Description|SAG-100WM|SAG-1000|Related documentation|
|-------|--------|-----------|---------|--------|---------------------|
|Basic connectivity|Static IP address for the port|Configure a static IP address for the port.|√|√| [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 [SAG-1000 configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-1000 configurations/Configuration process.md#)

 |
|PPPoE connections through WAN port|Access the Internet through broadband \(dial-up mode\).|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 |
|4G support|Access the Internet by using a 4G connection.|√ Built-in LTE

 |√ External LTE

 | [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 [Configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-1000 configurations/Configuration process.md#)

 |
|LAN port DHCP|Newly established sites automatically obtain the IP address.|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 |
|Wi-Fi access|Access the Internet through Wi-Fi.|√|×| [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 |
|Static routing|The existing on-premises networks are connected through static routing.|√|√| [SAG-100WM configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/Configuration process.md#)

 [SAG-1000 configuration guide](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-1000 configurations/Configuration process.md#)

 |
|OSPF|Support the OSPF protocol.|×|√|[Web configurations for SAG-1000 devices](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-1000 configurations/Web configurations for SAG-1000 devices.md#)|
|Internet SNAT|Access the Internet through the inline networking mode.|√|×| [SAG-100WM inline configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

 |
|Cross-region access to VPC|Access from one point to connect target VPCs around the globe through the intranet.|√|√| [Cross-border access to VPC](../../../../reseller.en-US/Best Practices/Cross-region access to VPC.md#)

 |
|Access control|Allow or forbid IP addresses in access control list \(ACL\) rules to access the Internet or intranet.|√|√|[Configure an access control list](../../../../reseller.en-US/Access control list/Configure an access control list.md#)|
|Configuration|Zero Touch Provisioning \(ZTP\)|Zero-configuration deployment.|√|×| -

 |
|Networking mode|Inline mode|Newly established sites use an SAG as an egress to access Alibaba Cloud.|√|×| [SAG-100WM inline configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

 |
|One-arm mode|The existing sites access Alibaba Cloud through an SAG without changing the existing network architecture.|×|√| [SAG-1000 dual-device one-arm mode configuration tutorial](../../../../reseller.en-US/Best Practices/SAG-1000 dual-device one-arm dynamic-routing hot-backup configuration tutorial/Configuration overview.md#)

 |
|High availability|Physical connection backup|Add an SAG as the backup link of an existing physical connection.|×|√| -

 |
|Dual-link backup - WAN + 4G|An SAG instance uses dual links formed by broadband and 4G to access the Internet.|√|Coming soon|[View the WAN + 4G backup of an SAG](../../../../reseller.en-US/Smart Access Gateway/High availability configurations/View the WAN + 4G backup of an SAG.md#)|
|Dual-device cold backup|The two devices share the bandwidth and operate in active/standby mode. If the active device fails, traffic is immediately directed to the standby device.|√|×|[View the HA configuration of an SAG](../../../../reseller.en-US/Smart Access Gateway/High availability configurations/View the HA configuration of an SAG.md#)|
|Dual-device hot backup|The two devices share the bandwidth and are online at the same time to perform automatic detection and switching.|×|√|[View the HA configuration of an SAG](../../../../reseller.en-US/Smart Access Gateway/High availability configurations/View the HA configuration of an SAG.md#)|
|ECC + In|The two devices share the bandwidth and are online at the same time to perform automatic detection and switching.|×|√|[View leased line backup](../../../../reseller.en-US/Smart Access Gateway/High availability configurations/View leased line backup.md#)|
|Security|VPN encryption|The connection is encrypted.|√|√| -

 |
|Access control|Intranet ACL management.|√|√| -

 |
|Offline device locking|Anti-theft with offline locking.|√|√|-|
|Operation and maintenance|Remote restart|Restart the device through the console.|√|√|[Restart an SAG remotely](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/Device management/Restart an SAG remotely.md#)|
|Remote software upgrading|Upgrade the software through the console.|√|√|[Update the software of an SAG device](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/Device management/Update the software of an SAG device.md#)|
|Query the traffic|Query used traffic.|√|√|[View the monitoring data of an SAG instance](../../../../reseller.en-US/Smart Access Gateway/SAG Monitoring/View the monitoring data of an SAG instance.md#)|
|Monitoring|Device level monitoring|Send notifications if both the active and standby IPSEC links of an SAG device fail.|√|√| [Create an event alert](../../../../reseller.en-US/Smart Access Gateway/SAG Monitoring/Create an event alert.md#)

 |
|Link level monitoring|Send notifications when the device is online.|√|√| [Create an event alert](../../../../reseller.en-US/Smart Access Gateway/SAG Monitoring/Create an event alert.md#)

 |

