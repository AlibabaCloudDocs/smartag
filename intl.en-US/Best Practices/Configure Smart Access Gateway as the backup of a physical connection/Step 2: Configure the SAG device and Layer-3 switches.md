# Step 2: Configure the SAG device and Layer-3 switches {#concept_rcp_fpw_rfb .concept}

This tutorial shows you how to configure the routes of the Smart Access Gateway \(SAG\) device and its peer switches.

## Configure the SAG device {#section_s3v_l4w_mfb .section}

To configure the SAG device, follow these steps:

1.  After receiving the SAG device, follow [SAG-1000 user manual](../reseller.en-US/Product Introduction/Smart Access Gateway device/SAG-1000.md#) to check if all the accessories are provided, and then power on the SAG device.
2.  Connect port G3 of the SAG device to port G11 of switch A, and connect port G4 of the device to port G12 of switch B.
3.  Connect the network card of the PC to port 2 of the SAG device, and set the IP address of the network card to 192.168.0.100/24.
4.  Open your browser and enter the web configuration address of the SAG device.

    The default IP address is https: // 192.168.0.1. For more information, see [Log on to the web configuration page](../reseller.en-US//Step 2: Set the password when you log on for the first time.md#).

5.  Configure the service IP address and the management port.

    In this tutorial, set the service IP address to 192.168.101.1, set the management IP address to 192.168.20.1/24, and set the next hop to 192.168.20.4.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41718/156571446941206_en-US.png)

    |Configuration|Description|
    |:------------|:----------|
    |**Configure Service IP:**|The service IP address is used to establish the VPN tunnel.|
    |**Management Interface:**|The management port is used for the local client to access the Web console. Port 2 is the management port by default.|
    |**Management port IP:**|The management IP address is used for the local client to access the Web console.|
    |**Isolate or not:**|Select whether to isolate the service port from the management port:     -   **Yes**: This port can only be used as a local Web management port and cannot be used as a service port.

In the isolation mode, the service traffic and the management traffic do not communicate with each other, thus achieving a higher level of security.

    -   **No**: This port is used as both the local Web management port and the service port.
 |
    |**Next Hop**|If you choose to isolate the service port from the management port, specify the next hop of the management port.|

6.  Configure the ports used to communicate with the switches:
    -   **Connection Type**: Select static or dynamic routing. In this tutorial, select **Dynamic Route**.
    -   **Port**: Click the **Edit** option in the **Configurations** area, enter the IP addresses of the ports used for communication and select whether to enable Open Shortest Path First \(OSPF\).

        In this tutorial, OSPF is enabled. The IP addresses of the ports used for communicating with the switches are 192.168.11.2/24 and 192.168.12.2/24.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41718/156571447041252_en-US.png)

7.  Configure OSPF.

    In this tutorial, MD5 authentication is selected, and the service IP address used by the RouterID is 192.168.101.1.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41718/156571447041207_en-US.png)

    |Configuration|Description|
    |:------------|:----------|
    |**Connection method**|Choose to access the switch using static or dynamic routing.**Notice:** When dual-device one-arm mode is used, only dynamic routing is supported.

|
    |**Port**|Click the **Edit** option in the **Configuration Information** area, enter the IP address of the port used for communication and select whether to enable OSPF.Port 2 is the default management port.

|
    |OSPF routing configuration|
    |**Area ID**|The ID of the area.Make sure that area IDs of SAG device 1 and SAG device 2 are different and the area ID of each SAG device is the same as that of the corresponding peer switch.

|
    |**Hello\_time**|The interval at which hello packets are sent, in seconds.Default value: 3 seconds.

|
    |**Dead\_time**|The dead interval of OSPF neighbor, in seconds. The neighbor relation stops if no hello packet is received during the dead time.Default value: 10 seconds.

|
    |**Authentication method**|Select an authentication method.    -   **Do not authenticate**: Do not perform authentication.
    -   **Clear Text Authentication**: Enter a clear text password.
    -   **MD5 Authentication**: Use the MD5 method to perform authentication. Enter the MD5 key ID and the MD5 key.
|
    |**Routerid**|The ID of the OSPF router. We recommend that you directly use the service IP address.|
    |**Area Type**|The area type is nssa by default.|


## Configure the peer switches {#section_olk_k4w_mfb .section}

Add route configurations for the peer switches of the device according to the following configurations. Here a switch is taken as an example. For switches of other manufacturers, see the device manuals for specific configurations.

-   Route configurations of the peer switches.

    **Note:** You must configure the network type of the interfaces using the OSPF protocol on the same Smart Access Gateway device to p2p, otherwise the routes cannot be correctly calculated.

    ``` {#codeblock_sru_qvi_5k0}
    interface GigabitEthernet 0/11
     no switchport
     ip ospf network point-to-point
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf hello-interval 3
     ip ospf dead-interval 10
     ip address 192.168.11.1 255.255.255.0  The IP address of the port on the peer switch of the SAG device
    
    interface GigabitEthernet 0/12
     no switchport
     ip ospf network point-to-point
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf hello-interval 3
     ip ospf dead-interval 10
     ip address 192.168.12.1 255.255.255.0   The IP address of the port on the peer switch of the SAG device
    						
    ```

-   Configure the loopback address of the switch.

    **Note:** You must configure OSPF to be in the NSSA area and to automatically generate default routes and advertise them to the SAG device.

    ``` {#codeblock_9bc_0u8_ace}
    interface Loopback 0
    ip address 192.168.101.3 255.255.255.255                       The loopback address of the switch
    router ospf 1
     router-id 192.168.101.3                                  The router ID of the switch
     area 0
     area 1
     area 1 nssa translator always default-information-originate
     network 192.168.3.0 0.0.0.255 area 0                     The CIDR block of the local PC
     network 192.168.11.0 0.0.0.255 area 1                        The CIDR block of the switch
     network 192.168.12.0 0.0.0.255 area 1
     network 192.168.13.0 0.0.0.255 area 1
     network 192.168.14.0 0.0.0.255 area 1
     network 192.168.100.0 0.0.0.255 area 0                      The CIDR block used for communicating with the uplink router
     network 192.168.101.3 0.0.0.0 area 0                        The loopback address of the switch
     default-information originate always                        Advertise default routes to the SAG device
    ```


