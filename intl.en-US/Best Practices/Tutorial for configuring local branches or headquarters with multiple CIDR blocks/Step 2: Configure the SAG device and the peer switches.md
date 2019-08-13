# Step 2: Configure the SAG device and the peer switches {#concept_rcp_fpw_rfb .concept}

After receiving the Smart Access Gateway \(SAG\) device, you need to configure its WAN and LAN ports and add related routing configurations to the switch.

## Configure the SAG device {#section_scp_fpw_rfb .section}

To configure the SAG device, follow these steps:

1.  After receiving the SAG device, follow [SAG-100WM overview](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/SAG-100WM configurations/SAG-100WM overview.md#) to check if all accessories are provided and then power on the device.
2.  Connect the WAN port of the SAG device to the network cable and connect a LAN port to a client used for web configuration.
3.  Open your browser and enter the web configuration address of the SAG device.

    The default address is https: // 192.168.0.1. For more information, see [Log on to the web configuration page](../../../../reseller.en-US//Step 2: Set the password upon your first logon.md#).

4.  Click **WAN Port Management** to configure the method for connecting to the Internet.

    In this tutorial, the WAN port uses a dynamic IP address allocated from the Internet router through DHCP to access the Internet. For more information, see [Configure the WAN port](../../../../reseller.en-US//Step 3: Configure the WAN ports.md#):

5.  Click **LAN Port Management**. In this tutorial, disable the wireless function. The configurations are as follows:
    -   **Connection Type**: Select **Static IP**.
    -   **LAN Address**: In this tutorial, enter **10.0.13.1**.
    -   **Configure Routes**: Click **Configure Routes** and add two static routes. The destination CIDR block of each route is the CIDR block of the corresponding client and the next hop of each route is the IP address of the port on the peer switch connected to the SAG device.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/60912/156571420930635_en-US.png)


## Configure the switches {#section_xdp_fpw_rfb .section}

Add two routes on each switch and one of them is the default route. The next hop of the default route is the static IP address of the LAN port of the SAG device and the next hop of the other route is the IP address of the port on the peer switch.

Route configuration of switch 1:

``` {#codeblock_qgq_jlr_6mh}

ip route 0.0.0.0/0 10.0.13.1
ip route 10.0.20.0/24 10.0.13.3
				
```

Route configuration of switch 2:

``` {#codeblock_g6u_gru_v4y}

ip route 0.0.0.0/0 10.0.13.1
ip route 10.0.10.0/24 10.0.13.2
				
```

