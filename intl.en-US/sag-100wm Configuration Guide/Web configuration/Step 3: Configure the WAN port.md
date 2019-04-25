# Step 3: Configure the WAN port {#task_uds_gf2_qfb .task}

The WAN port of Smart Access Gateway is used for configuring Internet access and supports dynamic IP addresses, static IP addresses, and PPPoE connections.

1.  Log on to the web configuration page of the Smart Access Gateway device. 
2.  Enter the logon password and click **OK**. 
3.  Click **WAN Port Management**. On the WAN Configuration page, configure the WAN port. 
4.  Select whether to enable SNAT forwarding. If SNAT forwarding is enabled, packets sent to the WAN from the LAN are forwarded by using NAT by default. 

    Select a connection mode:

    -   Dynamic IP address:

        Select this mode to allow access to the Internet by using an IP address allocated by a DHCP server from a router.

    -   Static IP address:

        Select this mode to allow access to the Internet by using a specified IP address. If this mode is selected, you must configure the subnet mask and gateway in addition to the Static IP address.

        **Note:** The specified static IP address and the uplink router device must be in the same CIDR block.

    -   PPPoE connection: Select this mode if you want to access the Internet by using dial-up. Afterwards, enter the PPPoE account and password given by the service provider.
5.  Click **OK**. 

