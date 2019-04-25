# Web configurations for SAG-1000 devices {#concept_lyd_3cz_mfb .concept}

You can configure service and administration ports for an SAG-1000 device. You can also configure static or OSPF routing for the device.

## Configure the service IP address and the administration port {#section_zl5_5cz_mfb .section}

After you log on to the Web configuration page of the SAG-1000 device, you can configure the service IP address and the administration port. Descriptions about the configuration items are provided in the following table.

|Configuration|Description|
|:------------|:----------|
|**Service IP address**|The service IP address is used to establish the VPN tunnel.**Note:** Make sure that the specified service IP can access the Internet. For one-arm mode, you must enable NAT mapping at the Internet egress.

|
|**Administration port**|The administration port is used for local clients to access the Web configuration page. Port 2 is the administration port.|
|**Administration IP address**|The administration IP address is used for local clients to access the Web configuration page..|
|**Whether to isolate**|You can select whether to isolate the service port from the administration port:-   **Yes**: This port can only be used as a local web administration port and cannot be used as a service port.

In the isolation mode, the service traffic and the administration traffic do not affect each other, so higher security is achieved.

-   **No**: This port is used as both the local web administration port and the service port.

|
|**Next hop**|If you choose to isolate the service port from the administration port, specify the next hop of the administration port.|

## Configure ports {#section_fx1_ddz_mfb .section}

There are six ports on the SAG-1000 device. Port 1 and Port 2 are optical module ports, and port 2 to port 5 are device ports. Descriptions about the configuration items are provided in the following table.

|Configuration|Description|
|:------------|:----------|
|**Connection method**|You can choose to use static or dynamic routing to access the switch.**Note:** If dual-device one-arm mode is used, only dynamic routing is supported.

|
|**Port**|You can click the **Edit** option in the **Configuration Information** area, enter the IP of the port used for communication and select whether to enable OSPF.Port 2 is the default administration port.

|

## Configure OSPF routing {#section_ryw_mdz_mfb .section}

|Configuration|Description|
|:------------|:----------|
|**Area ID**|The ID of the area.Make sure that area IDs of Smart Access Gateway device 1 and Smart Access Gateway device 2 are different.

|
|**Hello\_time**|The interval at which hello packets are sent, in seconds.|
|**dead\_time**|The dead time interval of the OSPF neighbor, in seconds. The neighbor relationship stops if no hello packet is received during the dead time interval.|
|**Authentication method**|You can select the required authentication method.-   **Do not authenticate**: Do not perform authentication.
-   **Clear Text Authentication**: Enter a clear text password.
-   **MD5 Authentication**: Use the MD5 algorithm to perform authentication. Enter the MD5 key ID and the MD5 key.

|
|**Routerid**|The ID of the OSPF router. We recommend that you directly use the service IP address.|
|**Area Type**|By default, the area type is NSSA.|

