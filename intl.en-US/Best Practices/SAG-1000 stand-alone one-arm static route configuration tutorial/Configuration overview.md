# Configuration overview {#concept_frd_cx4_fgb .concept}

This tutorial guides you in how to connect your headquarters or branches to Alibaba Cloud through SAG-1000 Smart Access Gateway.

## Scenarios {#section_xc3_bkz_k2b .section}

This tutorial takes the network architecture in the following figure as an example. Two Layer-3 switches form a switch stack and are connected to two Layer-2 switches. Local clients access the Internet through Layer-2 switches.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23710/155427792013772_en-US.png)

As shown in the following figure, one SAG-1000 Smart Access Gateway is connected to Layer-3 switches through one-arm mode to connect local servers to Alibaba Cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82225/155427792135023_en-US.png)

## Network planning {#section_vk5_441_mfb .section}

Before you begin, you must plan the following network configurations and ensure that the CIDR blocks do not conflict with one another:

-   The CIDR blocks of the VPCs to connect. In this tutorial, the CIDR blocks of the two VPCs are 192.168.0.0/24 and 10.0.0.0/24.
-   IPs of local servers/clients

    Plan the IPs of the local servers/clients according to your needs. In this tutorial, the IP 192.168.3.0/24 is used.

-   IPs used by the device to communicate with the Layer-3 switches

    Plan the IPs of the ports used by the Smart Access Gateway to communicate with the Layer-3 switches. We recommend that you set the mask to /30. In this tutorial, the port IPs used by the device are 192.168.11.2/24 and 192.168.12.2/24.

-   Service IP

    Plan the service IP of the Smart Access Gateway device. We recommend that you set the mask to /32. In this tutorial, the service port IP 192.168.101.1 is used.

-   Administration port IP

    Plan the administration port IP of the Smart Access Gateway device. You can use an independent administrator port IP or use the service port IP as the administrator port IP. In this tutorial, 192.168.0.1/24 is used as the administration port IP.


|Configuration|Example value|
|:------------|:------------|
|CIDR blocks of the VPCs| VPC1: 192.168.0.0/24

 VPC2: 10.0.0.0/24

 |
|The CIDR block of the egress router|192.168.100.253/24|
|The CIDR block used by the Layer-3 switches to communicate with Alibaba Cloud|192.168.100.100/24|
|The CIDR block used by the Layer-3 switches to communicate with Smart Access Gateway|192.168.3.1/24|
|IPs of the ports of the Smart Access Gateway| G3 192.168.11.2/24

 G4 192.168.12.2/24

 |
|IPs of the ports on the peer switches of the Smart Access Gateway| G11 192.168.11.1/24

 G12 192.168.12.1/24

 |
|The CIDR block of local servers|192.168.3.0/24|

