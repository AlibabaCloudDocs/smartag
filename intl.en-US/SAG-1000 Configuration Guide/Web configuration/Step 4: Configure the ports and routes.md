# Step 4: Configure the ports and routes {#task_vdn_kq1_qfb .task}

There are six ports on the SAG-1000 device. Port 0 and Port 1 are SFP optical ports, and Ports 2-5 are RJ45 electrical ports. You can configure a static route or OSPF routes for port connection.

1.  Log on to the Web console of the SAG device, click the **Configuration** tab page, and then click **Port Management**. 
2.  Configure the ports of the SAG device and then click **OK**. Descriptions about the configuration items are provided in the following table. 

    |Configuration|Description|
    |:------------|:----------|
    |**Connection method**|Choose to access the switch using static or dynamic routing.**Notice:** When dual-device one-arm mode is used, only dynamic routing is supported.

|
    |**Port**|Click the **Edit** option in the **Configuration Information** area, enter the IP of the port used for communication and select whether to enable OSPF.Port 2 is the default administrator port.

|
    |OSPF routing configuration|
    |**Area ID**|The ID of the area.Make sure that area IDs of Smart Access Gateway 1 and Smart Access Gateway 2 are different and the area ID of each SAG device is the same as that of the corresponding peer switch.

|
    |**Hello\_time**|The interval at which hello packets are sent, in seconds.Default value: 3 seconds.

|
    |**Dead\_time**|The dead interval of OSPF neighbor, in seconds. The neighbor relation stops if no hello packet is received during the dead time.Default value: 10 seconds.

|
    |**Authentication method**|Select an authentication method.    -   **Do not authenticate**: Do not perform authentication.
    -   **Clear Text Authentication**: Enter a clear text password.
    -   **MD5 Authentication**: Use the MD5 method to perform authentication. Enter the MD5 key ID and the MD5 key.
|
    |**Routerid**|The ID of the OSPF router. We recommend that you directly use the service IP.|
    |**Area Type**|The area type is nssa by default.|


