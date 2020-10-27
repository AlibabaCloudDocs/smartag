# Features of Smart Access Gateway devices

Smart Access Gateway \(SAG\) provides two models of devices. Supported features of each model are listed in the following table. "√" and "×" represent "supported" and "not supported".

|Feature|Function|Description|SAG-100WM|SAG-1000|
|Version 1.0 and later|Version 2.0 and later|Version 1.0 and later|Version 2.0 and later|
|-------|--------|-----------|---------|--------|
|---------------------|---------------------|---------------------|---------------------|
|Basic connectivity|Static IP addresses on ports|Configures static IP addresses on ports.|√|√|√|√|
|WAN port PPPoE|Accesses the Internet through dial-up connections provided by SAG devices.|√|√|×|√|
|4G support|Accesses the Internet through 4G networks.|√ Built-in Long Term Evolution \(LTE\)

|√ Built-in LTE

|√ External LTE

|√ Built-in LTE

**Note:** Supported by specific devices. |
|LAN ports support Dynamic Host Configuration Protocol \(DHCP\)|Newly established private networks automatically obtain IP addresses.|√|√|×|√|
|Wi-Fi support|On-premises devices connect to Alibaba Cloud through Wi-Fi connections.|√|√|×|×|
|Static routes|Existing private networks connect to Alibaba Cloud through static routing.|√|√|√|√|
|OSPF|Supports the Open Shortest Path First \(OSPF\) protocol.|×|√|√|√|
|BGP|Supports the Border Gateway Protocol \(BGP\).|×|√|√|√|
|Internet SNAT|Allows private networks to access the Internet when SAG devices are deployed in inline mode.|√|√|×|√|
|Cross-region access to virtual private clouds \(VPCs\)|Private networks can access VPCs from different regions.|√|√|√|√|
|Parameter|Zero touch provisioning \(ZTP\)|Supports ZTP in SAG deployment.|√|√|×|√|
|Deployment modes of SAG devices|Inline mode|New private networks connect to Alibaba Cloud through SAG devices. All traffic is transmitted through SAG devices.|√|√|×|√|
|One-arm mode|Private networks connect to Alibaba Cloud through SAG devices, without changing the existing network topology.|√|√|√|√|
|High availability \(HA\)|Standby network connections provided by SAG devices|SAG devices can provide standby network connections for existing leased lines.|√|√|√|√|
|Supports active and standby networks: WAN and 4G networks|An SAG device uses broadband or 4G networks to access the Internet.|√|√|√ External LTE

|√ Built-in LTE |
|Active and standby devices|The active device is connected to Alibaba Cloud. When the active device is malfunctioning, the standby device takes over. This ensures the high availability of your workloads.|√|√|√|√|
|Security|VPN encryption|Supports encrypted VPN connections.|√|√|√|√|
|Access control lists \(ACLs\)|Allows or denies access to the Internet or private networks based on ACL rules.|√|√|× **Note:** Internet ACLs are not supported.

|√|
|Offline device locking|Locks devices that are offline for a long time to prevent theft.|√|√|√|√|
|Operations and maintenance|Remote restart|Restarts a device remotely in the console.|√|√|√|√|
|Remote software updates|Remotely updates the software version in the console.|√|√|√|√|
|Remote logons|Logs on to the web console through a secure internal connection.|√|√|√|√|
|Traffic query|Queries data usage.|√|√|√|√|
|Flow log|Records inbound and outbound traffic of SAG devices.|×|×|√|√|
|QoS policies|Distinguishes traffic of different workloads and ensures sufficient bandwidth for high-priority traffic.|√|√|√|√|
|Traffic monitoring|Device monitoring|Checks whether both the active and standby IPsec connections encounter an error.|√|√|√|√|
|Connection monitoring|Notifications are sent when an SAG device is online.|√|√|√|√|
|Health checks**Note:** The health check feature is disabled by default. To enable this feature, [submit](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308) a ticket.

|Checks the connectivity of connections.|×|√|×|√|

