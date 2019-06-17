# Step 3: Configure the SAG device \(device 2\) and its peer switches {#concept_ql4_g4w_mfb .concept}

This tutorial describes how to configure the routes of Smart Access Gateway \(SAG\) device 2 \(known as device 2 in this topic\) and its peer switches.

## Configure the SAG device {#section_s3v_l4w_mfb .section}

To configure device 2, follow these steps:

1.  After receiving device 2, follow [SAG-1000 user manual](../intl.en-US/Product Introduction/Smart Access Gateway device/SAG-1000.md#) to check that all accessories are provided and then power on the device.
2.  Connect port G3 of device 2 to port G13 of switch A, and connect port G4 of device 2 to port G14 of switch B.
3.  Connect the network card of the PC to port 2 of device 2 and set the IP address of the network card to 192.168.0.100/24.
4.  Enter the web configuration address of device 2 in your browser.

    The default address is https: //192.168.0.1. For more information, see [Log on to the web configuration page](../intl.en-US/SAG-1000 Configuration Guide/Web configuration/Step 2: Set the password when you log on for the first time.md#).

5.  Configure the service IP address and the management port.

    In this tutorial, set the service IP address to 192.168.101.2, set the management IP address to 192.168.20.2/24, and set the next hop to 192.168.20.4.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23999/156074093713925_en-US.png)

    |Configuration|Description|
    |:------------|:----------|
    |**Configure Service IP:**|The service IP address is used to establish the VPN tunnel.|
    |**Management Interface:**|The management port that the local client uses to access the Web console. Port 2 is the management port by default.|
    |**Management port IP:**|The management IP address that the local client uses to access the Web console.|
    |**Isolate or not:**|Select whether to isolate the service port from the management port:     -   **Yes**: This port can only be used as a local Web management port and cannot be used as a service port.

In the isolation mode, the service traffic and the management traffic do not communicate with each other, achieving a high level of security.

    -   **No**: This port is used as both the local Web management port and the service port.
 |
    |**Next Hop**|If you choose to isolate the service port from the management port, you must specify the next hop of the management port.|

6.  Configure the ports used to communicate with the switches:
    -   **Connection Mode**: Select static or dynamic routes. In this tutorial, select **Dynamic Routing**.
    -   **Port**: Click the **Edit** option in the **Configuration Information** area, enter the IP addresses of the ports used for communication and select whether to enable OSPF.

        In this tutorial, OSPF is enabled and the ports used for communicating with the switches are 192.168.13.2/24 and 192.168.14.2/24.

        ![](images/13926_en-US.png)

7.  Configure OSPF.

    In this tutorial, MD5 authentication is selected. Enter the service IP address 192.168.101.2 as the RouterId.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23999/156074093713927_en-US.png)

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


## Configure the peer switches \(Ruijie\) {#section_olk_k4w_mfb .section}

After you have configured device 2, you need to add route configurations for the peer switches of device 2 according to the following configurations. For switches of different manufacturers, see the device manuals for specific configurations.

-   Route configurations of the peer switches.

    **Note:** You must configure the network type of the interfaces using the OSPF protocol on the same Smart Access Gateway device to p2p, otherwise the routes cannot be correctly calculated.

    ```
    
    interface GigabitEthernet 0/13
     no switchport
     ip ospf network point-to-point   The network type must be p2p
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf hello-interval 3
     ip ospf dead-interval 10
     ip address 192.168.13.1 255.255.255.0    The IP address of port on the peer switch of the SAG device
    
    interface GigabitEthernet 0/14
     no switchport
     ip ospf network point-to-point    The network type must be p2p
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf hello-interval 3
     ip ospf dead-interval 10
     ip address 192.168.14.1 255.255.255.0  The IP address of the port on the peer switch of the SAG device
    ```

-   Configure the loopback address of the switch.

    **Note:** You must configure OSPF to be in the NSSA area and to automatically generate default routes and advertise the routes to the SAG device.

    ```
    interface Loopback 0
    ip address 192.168.101.3 255.255.255.255                       The loopback address of the switch
    router ospf 1
    router-id 192.168.101.4                                       The router ID of the switch
     area 0
     area 1
     area 2
     area 2 nssa translator always default-information-originate
     area 1 nssa translator always default-information-originate
     network 192.168.3.0 0.0.0.255 area 0                     The CIDR block of the local PC
     network 192.168.11.0 0.0.0.255 area 1                        The CIDR block of the switch
     network 192.168.12.0 0.0.0.255 area 1
     network 192.168.13.0 0.0.0.255 area 2
     network 192.168.14.0 0.0.0.255 area 2
     network 192.168.100.0 0.0.0.255 area 0                      The CIDR block used for communicating with the uplink router
     network 192.168.101.3 0.0.0.0 area 0                        The loopback address of the switch
     default-information originate always                        Advertise default routes to the SAG device
    ```


## Configure the peer switches \(Cisco\) {#section_x5u_tts_vgr .section}

After you have configured device 2, you need to add route configurations for the peer switches of device 2 according to the following configurations. For switches of different manufacturers, see the device manuals for specific configurations.

-   Route configurations of the peer switches.

    **Note:** You must configure the network type of the interfaces using the OSPF protocol on the same Smart Access Gateway device to p2p, otherwise the routes cannot be correctly calculated.

    ``` {#codeblock_pp2_a9x_f01}
    interface GigabitEthernet 0/13
     no switchport
     ip address 192.168.11.1 255.255.255.0 The IP address of the port on the peer switch of the Smart Access Gateway device
     ip ospf network point-to-point    The network type must be p2p
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf dead-interval 10
     ip ospf hello-interval 3
    !
    interface GigabitEthernet 0/14
     no switchport
     ip address 192.168.11.1 255.255.255.0 The IP address of the port on the peer switch of the Smart Access Gateway device
     ip ospf network point-to-point    The network type must be p2p
     ip ospf authentication message-digest
     ip ospf message-digest-key 7 md5 1234
     ip ospf dead-interval 10
     ip ospf hello-interval 3
    !
    ```

-   Configure the loopback address of the switch.

    **Note:** You must configure OSPF to be in the NSSA area and to automatically generate default routes and advertise the routes to the Smart Access Gateway device.

    ``` {#codeblock_2an_88r_fyn}
    interface Loopback 0
    ip address 192.168.101.3 255.255.255.255                       The loopback address of the switch
    !
    router ospf 1
     router-id 192.168.101.3                                  The router ID of the switch
     area 2 nssa default-information-originate no-summary         Advertise default routes to the Smart Access Gateway device
     network 192.168.3.0 0.0.0.255 area 0                     The CIDR block of the local PC
     network 192.168.11.0 0.0.0.255 area 1                        The CIDR block of the switch
     network 192.168.12.0 0.0.0.255 area 1
     network 192.168.100.0 0.0.0.255 area 0                      The CIDR block used for communicating with the uplink router
     network 192.168.101.3 0.0.0.0 area 0                        The loopback address of the switch
     network 192.168.11.0 0.0.0.255 area 2                        The CIDR block of the switch
     network 192.168.14.0 0.0.0.255 area 2
     default-information originate always
    !
    ```


