# Configuration overview {#concept_hxx_njz_k2b .concept}

This tutorial shows you how to use the Smart Access Gateway \(SAG\) device as the backup link of an existing physical connection to access Alibaba Cloud and build a high-availability hybrid cloud.

## Scenarios {#section_kyb_3sy_rfb .section}

This tutorial uses the network architecture shown in the following figure as an example. In the example, the on-premises data center is already connected to Alibaba Cloud through a physical connection by using Express Connect. To ensure high service availability and avoid unnecessary changes to the network architecture, the Smart Access Gateway \(SAG-1000\) device is connected to a Layer-3 switch by using the one-arm mode and connected to Alibaba Cloud as a backup to the existing physical connection.

**Note:** 

-   Only an SAG-1000 device can form active and standby links with a leased line.
-   Only access through the physical connection of Cloud Enterprise Network \(CEN\) is supported. Access through Express Connect is not supported.
-   Make sure that Border Gateway Protocol \(BGP\) has been configured for the Virtual Border Router \(VBR\) of the leased line. If a static route is configured for the VBR, the VBR cannot be used as a backup leased line.

The flow direction of network traffic in this tutorial is as follows:

-   To Alibaba Cloud:

    By default, the routing priority is configured on the core switch of your on-premises data center, and traffic is distributed to Alibaba Cloud through the physical connection. If the physical connection fails, traffic is encrypted and then distributed to Alibaba Cloud over the Internet.

-   To the on-premises data center:

    By default, the CEN gives higher priority to routing through the physical connection, rather than through the CCN. More specifically, the traffic is distributed to your on-premises data center through the physical connection. If the physical connection fails, traffic is encrypted and then distributed to Alibaba Cloud \(to the CCN instance\) over the Internet.


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41687/156524250221633_en-US.png)

## Network planning {#section_ofx_msy_rfb .section}

Before you begin, you must plan the following network configurations and ensure that the CIDR blocks do not conflict with one another:

-   The CIDR block of the VPC to connect. In this tutorial, the CIDR block of the VPC is 192.168.0.0/24.
-   Local server/client IP address

    Plan the IP address of the local server/client as needed. In this tutorial, the IP address 192.168.3.0/24 is used.

-   The IP address used by the device to connect to the Layer-3 switches

    Plan the IP address of the port used by the SAG device to communicate with the Layer-3 switches. In this tutorial, the IP address of service port 3 used by the device is 192.168.11.2/24.

-   The IP address used by the Layer-3 switches to connect to Alibaba Cloud

    Make sure that the IP address used by the Layer-3 switches to connect to Alibaba Cloud and the IP address of the WAN port are in the same CIDR block. In this tutorial, the Layer-3 switches use the IP address 172.16.0.254 to access Alibaba Cloud.


|Configuration|Example value|
|:------------|:------------|
|The CIDR block of the VPC|192.168.0.0/24|
|The CIDR block of the egress router|192.168.100.253/24|
|The CIDR block used by the Layer-3 switches to communicate with Alibaba Cloud|192.168.100.100/24|
|The CIDR block used by the Layer-3 switches to communicate with the SAG device|192.168.3.1/24|
|IP addresses of the ports used by SAG device 1| G3 192.168.11.2/24

 G4 192.168.12.2/24

 |
|IP addresses of the ports used by SAG device 2| G3 192.168.13.2/24

 G4 192.168.14.2/24

 |
|IP addresses of the ports used by the peer switches of the SAG devices| G11 192.168.11.1/24

 G12 192.168.12.1/24

 G13 192.168.13.1/24

 G14 192.168.14.1/24

 |
|The CIDR block of local servers|192.168.3.0/24|

