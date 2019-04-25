# Features {#concept_ejm_bhs_j2b .concept}

Smart Access Gateway provides gateway devices of two models. The following table describes the differences in functionality between the device models:

|Feature|Specific function|Description|SAG-100WM|SAG-1000|Related documents|
|-------|-----------------|-----------|---------|--------|-----------------|
|Basic connectivity|Static IP address for port|Configure a static IP address for the port|√|√| [SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)

 [SAG-1000 configuration guide](../../../../intl.en-US/SAG-1000 Configuration Guide/Configuration guide.md#)

 |
|PPPoE connections through WAN port|Access the Internet through broadband \(dial-up mode\)|√|×| [SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)

 |
|4G support|Access the Internet by using a 4G connection|√Built-in LTE

|×External LTE

|[SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)|
|LAN port DHCP|A newly established site automatically obtains the IP address|√|×|[SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)

|
|WIFI access|Access the Internet through Wi-Fi|√|×|[SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)|
|Static routing|Existing on-premises networks are connected through static routing.|√|√| [SAG-100WM configuration guide](../../../../intl.en-US/sag-100wm Configuration Guide/Configuration guide.md#)

 [SAG-1000 configuration guide](../../../../intl.en-US/SAG-1000 Configuration Guide/Configuration guide.md#)

 |
|OSPF|Support OSPF protocol|×|√|[SAG-1000 web configuration](../../../../intl.en-US/User Guide/Configure a Smart Access Gateway device/Web configurations for SAG-1000 devices.md#)|
|Internet SNAT|Access the Internet through the inline networking mode|√|×|[SAG-100WM inline configuration tutorial](../../../../intl.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

|
|Cross-region access to VPC|Access from one point to connect target VPCs around the globe through the intranet|√|√|[Cross-border access to VPC](../../../../intl.en-US/Best Practices/Cross-region access to VPC.md#)|
|Access control|Allow or forbid IP addresses in the access control list to access the Internet or intranet|√|√|[Configure access control](../../../../intl.en-US/User Guide/Access control list (ACL)/Configure an access control list.md#)|
|Configuration|ZTP \(Zero Touch Provisioning\)|Zero-configuration deployment|√|×|-|
|Networking mode|Inline mode|A newly established site uses Smart Access Gateway as the egress by which to access Alibaba Cloud|√|×|[SAG-100WM inline configuration tutorial](../../../../intl.en-US/Best Practices/SAG-100WM inline mode configuration tutorial.md#)

|
|One-arm mode|An existing site accesses Alibaba Cloud through Smart Access Gateway without changing the existing network architecture|×|√|[SAG-1000 dual-device one-arm mode configuration tutorial](../../../../intl.en-US/Best Practices/SAG-1000 dual-device one-arm mode configuration tutorial/Configuration overview.md#)

|
|High availability|Physical connection backup|Add Smart Access Gateway as the backup link of an existing physical connection.|×|√|-|
|Dual-link backup-WAN + 4G|A Smart Access Gateway instance uses dual links formed by broadband and 4G to access the Internet.|√|Coming soon|[Device-level configurations for high availability](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Device-level configurations for high availability.md#)|
|Dual-device cold backup|The two devices share the bandwidth and operate in active/standby mode. This means if the active device fails, traffic is immediately directed to the standby device.|√|×|[Device-level configurations for high availability](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Device-level configurations for high availability.md#)|
|Dual-device hot backup|The two devices share the bandwidth and are online at the same time. Automatic detection and automatic switching are performed.|×|√|[Device-level configurations for high availability](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Device-level configurations for high availability.md#)|
|Security|VPN encryption|The connection is encrypted.|√|√|-|
|Access control|Intranet ACL management|√|√|-|
|Offline device locking|Anti-theft, offline locking|√|√|[Lock an offline device](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Lock an offline device.md#)|
|Operation and maintenance|Remote reboot|Reboot the device on the console|√|√|[Reboot through the console](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Reboot through the console.md#)|
|Remote software upgrading|Upgrade the software version on the console|√|√|[Upgrade the software version](../../../../intl.en-US/User Guide/Manage a Smart Access Gateway instance/Upgrade the software version.md#)|
|Query the traffic|Query used traffic|√|√|[Monitor traffic](../../../../intl.en-US/Troubleshooting/Alarm management/Monitor traffic.md#)|
|Monitoring|Device level monitoring|Send notifications if both the active and standby IPSEC links of Smart Access Gateway fail.|√|√|[Create an event alert](../../../../intl.en-US/Troubleshooting/Alarm management/Create an event alert.md#)|
|Link level monitoring|Send notifications when the device is online.|√|√|[Create an event alert](../../../../intl.en-US/Troubleshooting/Alarm management/Create an event alert.md#)|

