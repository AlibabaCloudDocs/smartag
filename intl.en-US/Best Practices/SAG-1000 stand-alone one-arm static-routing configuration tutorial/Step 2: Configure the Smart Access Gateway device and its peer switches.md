# Step 2: Configure the Smart Access Gateway device and its peer switches {#concept_xcx_lx4_fgb .concept}

This tutorial shows you how to configure the Smart Access Gateway\(SAG\) device and its peer switches.

## Configure the SAG device {#section_s3v_l4w_mfb .section}

To configure the SAG device, follow these steps:

1.  After receiving the SAG device, follow [SAG-1000 user manual](../reseller.en-US/Product Introduction/Smart Access Gateway device/SAG-1000.md#) to check if all accessories are provided and then power on the SAG device.
2.  Connect port G3 of the Smart Access Gateway to port G11 of switch A, and connect port G4 of the Smart Access Gateway to port G12 of switch B.
3.  Connect the network card of the PC to port 2 of the SAG device, and set the IP address of the network card to 192.168.0.100/24.
4.  Enter the web configuration address of the SAG device in the browser.

    The default address is https: // 192.168.0.1. For more information, see [Log on to the web configuration page](../reseller.en-US//Step 2: Set the password when you log on for the first time.md#).

5.  Configure the service IP address and the management port.

    In this tutorial, enter 192.168.101.1 as the service IP address, enter 192.168.20.1/24 as the management IP address, and enter 192.168.20.4 as the next hop.

    **Note:** The specified service IP address must be able to access the Internet. For one-arm mode, if the service IP address is a private CIDR block, you must enable NAT mapping at the Internet egress or firewall.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82227/156571060441191_en-US.png)

    |Configuration|Description|
    |:------------|:----------|
    |**Configure Service IP:**|The service IP address is used to establish the VPN tunnel.**Note:** Make sure that the specified service IP address can access the Internet.

|
    |**Management Interface:**|The management port is used for local clients to access the Web console. By default, port 2 is the management port.|
    |**Isolate or not:**|Select whether to isolate the service port from the management port:    -   **Yes**: This port can only be used as a local Web management port and cannot be used as a service port.

In the isolation mode, the service traffic and the management traffic do not communicate with each other, achieving a high level of security.

    -   **No**: This port is used as both the local Web management port and the service port.
|
    |**Management port IP:**|The management IP address is used for Web access of the local client.|
    |**Next Hop:**|If you choose to isolate the service port from the management port, specify the next hop of the management port.|

6.  Configure the ports used to communicate with the switches:
    -   **Connection Mode**: Select to use static routes.
    -   **Port**: Click the **Edit** option in the **Configuration Information** area.

        The specified ports are 192.168.11.2/24 and 192.168.12.2/24.


## Configure the peer switches {#section_olk_k4w_mfb .section}

Add route configurations for the peer switches of the device according to the following configurations. Here a Ruijie switch is taken as an example. For devices of other manufacturers, see the device manuals for specific configurations.

Route configurations of the peer switches.

``` {#codeblock_ett_lz3_ynp}
interface GigabitEthernet 0/11
 no switchport
 ip address 192.168.11.1 255.255.255.0 The IP address of the port on the peer switch of the SAG device

interface GigabitEthernet 0/12
 no switchport
 ip address 192.168.12.1 255.255.255.0  The IP address of the port on the peer switch of the SAG device

ip route 192.168.101.2 255.255.255.255 192.168.11.2  The route from the switch to the service IP address
ip route 192.168.101.1 255.255.255.255 192.168.12.2 

ip route 192.168.0.0 255.255.255.0 192.168.11.2  The route from the switch to VPC1
ip route 192.168.0.0 255.255.255.0 192.168.12.2 

ip route 10.0.0.0 255.255.255.0 192.168.11.2  The route from the switch to VPC2
ip route 10.0.0.0 255.255.255.0 192.168.12.2 
				
```

