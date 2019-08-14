# Configuration overview {#concept_hxx_njz_k2b .concept}

This tutorial guides you to connect your headquarters or branches to Alibaba Cloud through the SAG-1000 Smart Access Gateway.

## Scenarios {#section_xc3_bkz_k2b .section}

This tutorial takes the network architecture in the following figure as an example. Two Layer-3 switches form a switch stack and are connected to two Layer-2 switches. Local clients access the Internet through Layer-2 switches.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23710/156577364213772_en-US.png)

As shown in the following figure, two SAG-1000 Smart Access Gateways access Layer-3 switches through one-arm mode to connect local servers to Alibaba Cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23710/156577364213749_en-US.png)

## Network planning {#section_vk5_441_mfb .section}

Before you begin, you must plan the following network configurations and ensure that the CIDR blocks do not conflict with one another:

-   The CIDR blocks of the VPCs to connect. In this tutorial, the CIDR blocks of the two VPCs are 192.168.0.0/24 and 10.0.0.0/24.
-   IP addresses of local servers/clients

    Plan the IP addresses of the local servers/clients according to your needs. In this tutorial, the IP address 192.168.3.0/24 is used.

-   IP addresses used by the devices to communicate with the Layer-3 switches

    Plan the IP addresses of the ports used by the Smart Access Gateway devices to connect the Layer-3 switches. We recommend that you set the mask to /30. In this tutorial, the IP addresses of the ports used by device 1 are 192.168.11.2/24 and 192.168.12.2/24, and those of the ports used by device 2 are 192.168.13.2/24 and 192.168.14.2/24.

-   Service IP addresses

    Plan the service IP addresses of the Smart Access Gateway devices. In this tutorial, the service port IP addresses used by the devices are 192.168.101.1 and 192.168.101.2.

-   Management port IP addresses

    Plan the management port IP addresses of the Smart Access Gateway devices. You can use an independent management port IP address or use the service IP address as the in-band management port IP address. In this tutorial, the management port IP address used by device 1 is 192.168.20.1/24, and the one used by device 2 is 192.168.20.2/24.


|Configuration|Example value|
|:------------|:------------|
|CIDR blocks of the VPCs| VPC1: 192.168.0.0/24

 VPC2: 10.0.0.0/24

 |
|The CIDR block of the egress router|192.168.100.253/24|
|The CIDR block used by the Layer-3 switches to communicate with Alibaba Cloud|192.168.100.100/24|
|The CIDR block used by the Layer-3 switches to communicate with the Smart Access Gateway devices|192.168.3.1/24|
|IP addresses of the ports used by Smart Access Gateway device 1| G3 192.168.11.2/24

 G4 192.168.12.2/24

 |
|IP addresses of the ports used by Smart Access Gateway device 2| G3 192.168.13.2/24

 G4 192.168.14.2/24

 |
|IP addresses of the ports used by the peer switches of the Smart Access Gateway devices| G11 192.168.11.1/24

 G12 192.168.12.1/24

 G13 192.168.13.1/24

 G14 192.168.14.1/24

 |
|The CIDR block of local servers|192.168.3.0/24|

