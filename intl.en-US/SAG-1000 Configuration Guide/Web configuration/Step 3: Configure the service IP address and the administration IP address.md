# Step 3: Configure the service IP address and the administration IP address {#task_y5n_2p1_qfb .task}

After you configure the user name and password and log on to the web configuration page, you can configure the service IP address and administration IP address of the SAG device. By default, port 2 is the administration port.

1.  On the web configuration page, click **Service IP Configuration**. 
2.  Configure the service IP address and administration IP address, and then click **OK**. Descriptions about the configuration items are provided in the following table. 

    |Configuration|Description|
    |:------------|:----------|
    |**Service IP address**|The service IP address is used to establish the VPN tunnel.**Note:** Make sure that the specified service IP can access the Internet.

|
    |**Administration port**|The administration port is used for local clients to access the Web console. By default, port 2 is the administration port.|
    |**Administration IP**|The administration IP is used for web access of the local client.|
    |**Whether to isolate**|Select whether to isolate the service port from the administration port:    -   **Yes**: This port can only be used as a local web administration port and cannot be used as a service port.

In the isolation mode, the service traffic and the administration traffic do not have impact on each other, so higher security is achieved.

    -   **No**: This port is used as both the local web administration port and the service port.
|
    |**Next hop**|If you choose to isolate the service port from the administration port, specify the next hop of the administration port.|


