# Configuration overview {#concept_o32_svd_sfb .concept}

This tutorial guides you to connect local branches or headquarters with multiple private CIDR blocks to Alibaba Cloud.

## Scenario {#section_kyb_3sy_rfb .section}

This tutorial takes the network architecture in the following figure as an example. Clients of the local branches are connected to two different switches, and the two switches are connected to Alibaba Cloud directly through the Smart Access Gateway \(SAG\).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41807/156376353921882_en-US.png)

## Network planning {#section_ofx_msy_rfb .section}

Before you begin, you must plan the following network configurations and ensure that the CIDR blocks do not conflict with one another:

-   The CIDR block of the VPC to connect. In this tutorial, the CIDR block of the VPC is 172.16.0.0/24.
-   Local client IP address

    Plan the IP address of each local client according to your needs. In this tutorial, the CIDR blocks 10.0.10.0/24 and 10.0.20.0/24 are used.

-   The IP addresses of the ports on the SAG device

    Plan the IP addresses of the ports used by the SAG device to communicate with the Layer-3 switch. In this tutorial, the static IP address of the LAN port used by the SAG device is 10.0.13.1, and the WAN port of the SAG device accesses the Internet through DHCP.

-   The IP address of the switch

    Plan the IP addresses used by each switch to communicate with the SAG device and the IP addresses used by each switch to communicate with Alibaba Cloud.


|Configuration|Example value|
|:------------|:------------|
|The CIDR block of the VPC|172.16.0.0/24|
|The IP addresses of the ports on the SAG device| WAN port: Enable DHCP

 The static IP address used by the LAN port: 10.0.13.1/24

 |
|The CIDR blocks of switch 1| The IP address used for connecting to Alibaba Cloud: 10.0.13.2/24

 The IP address used for connecting to the SAG device: 10.0.10.1/24

 |
|The CIDR blocks of switch 2| The IP address used for connecting to Alibaba Cloud: 10.0.13.3/24

 The IP address used for connecting to the SAG device: 10.0.20.1/24

 |

