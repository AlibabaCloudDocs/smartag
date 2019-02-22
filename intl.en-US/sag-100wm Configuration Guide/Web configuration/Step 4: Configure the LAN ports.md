# Step 4: Configure the LAN ports {#task_i21_3f2_qfb .task}

The LAN ports are used for connecting the local clients.

1.  Log on to the web configuration page of the Smart Access Gateway device. 
2.  After the WAN port is configured, click **Next** to configure the LAN ports. 
3.  On the LAN Configuration page, configure the LAN ports. 
    -   Wi-Fi function

        The LAN ports are used for connecting local clients. If you enable the Wi-Fi function, configure the LAN ports according to the following information.

        |Configuration|Description|
        |:------------|:----------|
        |**SSID**|The name of the LAN. It is used for differentiating different networks and can be customized.|
        |**SSID broadcast**|Only after SSID broadcast is enabled can Wi-Fi devices search for the Wi-Fi signal of the SSID.|
        |**Authentication type**|WPA-PSK authentication and WPA2-PSK authentication are supported. The WPA2-PSK authentication features higher security.|
        |**Encryption algorithm**|         -   TKIP provides a packet key combining information integrity checking and rekeying mechanism.
        -   AES is an efficient encryption standard for Wi-Fi authorization.
 |
        |**Password**|Set the Wi-Fi password.|

    -   Wired mode

        The LAN ports are used for connecting local clients. If you use network cables to connect the LAN ports, select a connection mode:

        -   Dynamic IP address:

            The IP addresses used by the LAN ports are allocated from the first CIDR block in the network configuration of the console.

            If your local clients directly access Alibaba Cloud through Smart Access Gateway as shown in the following figure, use the default configuration.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15409/15508279686822_en-US.png)

        -   Static IP:

            If the IP address of the local client has been configured through the switch as shown in the following figure, use a static IP address.

            To use a static IP address, you must configure the static IP address and the route:

            -   Static IP: The IP address of the gateway device.

                **Note:** Make sure the static IP address does not conflict with any network connected to the gateway device.

            -   If the LAN ports are connected through **static IP**, you need to add a route to the Smart Access Gateway and the switch separately.
                -   Route configuration of Smart Access Gateway

                    On the LAN configuration page, click **Route configuration**. Add a route. The destination CIDR block of the route is the IP address of the client and the next hop of the route is the IP address of the switch.

                    If you have multiple clients, you must configure a route for each client.

                -   Route configuration of the switch
                    -   To connect the switch to VPC, you must add a route in the switch. The destination CIDR block of the route is the CIDR block of the VPC and the next hop is the static IP address of the LAN port.
                    -   If local branches want to connect with each other through Smart Access Gateway, add routes for the branches to the switch. The destination CIDR block of each route is the IP address of each local branch and the next hop of each route is the static IP address of each LAN port.

