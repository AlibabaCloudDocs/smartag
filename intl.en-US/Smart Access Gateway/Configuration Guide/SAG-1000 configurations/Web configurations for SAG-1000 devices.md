# Web configurations for SAG-1000 devices {#task_1340441 .task}

This topic describes the steps that you must follow to complete Web configurations for SAG-1000 devices. Before you access Alibaba Cloud through Smart Access Gateway \(SAG\) devices, you must complete Web configurations for the SAG devices.

## Step 1: Configure the local client {#section_6xu_c2m_hlr .section}

Before performing Web configurations on an SAG-1000 device, you must configure the static IP address of the local client to access the Web configurations.

-   Windows client configuration
    1.  In the lower-right corner, right-click the network connection icon, and then click **Open Network and Sharing Center**.
    2.  In the left-side panel, click **Change Adapter Settings**.
    3.  Right-click the connected network and then click **Properties**.
    4.  Double-click **Internet Protocol Version 4 \(TCP/IPv4\)**.
    5.  Select **Use the following IP addresses** and enter the static IP address and subnet mask to use.

        **Note:** Ensure that the IP address is in the management CIDR block of the SAG device \(the default management CIDR block is 192.168.0.0/24\) and does not conflict with other IP addresses, for example, 192.168.0.99. You do not need to configure the gateway and DNS.

        ![Windows client settings](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40454/156687189521109_en-US.png)

    6.  Click **OK**.
-   Mac client configuration
    1.  On the desktop, click the **System Preferences** icon, and then click **Network** in the Internet and Network section. **Open Network and Sharing Center**.
    2.  Click the connected network and then click **Advanced**.
    3.  On the Ethernet configuration page, click the **TCP/IP** tab.
    4.  From the **Configure IPv4** drop-down list, select **Manually**, and enter the static IP address and subnet mask to use.

        **Note:** Ensure that the IP address is in the management CIDR block of the SAG device \(the default management CIDR block is 192.168.0.0/24\) and does not conflict with other IP addresses, for example, 192.168.0.99. You do not need to configure the router and DNS.


## Step 2: Set the password upon your first logon {#section_k5v_j7u_n6b .section}

After you power on the SAG device for the first time, you must go to the Web console and set a logon password.

Before you log on to the Web console, make sure that:

-   The SAG device is powered on.
-   The static IP address is configured on the local client.
-   The local PC is connected to Port 2 of the SAG device through a network cable.

1.  Open the browser on the connected local PC and enter `192.168.0.1` in the address bar. 

    `192.168.0.1` is the default web configuration address of the SAG device.

2.  Enter a logon password. We recommend that you securely store your logon password and keep it strictly confidential. If the password is lost or forgotten, press the RESET button to clear the old password. Then, log on to the Web console and set a new password.

    **Note:** If you press the RESET button for three times or more within 10 seconds, all configurations are cleared.

3.  Log on to the Web console.

## Step 3: Configure the service IP address and the management IP address {#section_26i_e5g_sa4 .section}

After you configure the username and password and log on to the Web configuration page, you can configure the service IP address and management IP address of the SAG device. Port 2 is the management port by default.

1.  On the Web configuration page, click **Service IP**.
2.  Configure the service IP address and management IP address according to the following information, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Configure Service IP:**|The service IP address is used to establish the VPN tunnel. **Note:** Make sure that the specified service IP address can access the Internet.

 |
    |**Management Interface:**|The management port is used for local clients to access the Web console. By default, port 2 is the management port.|
    |**Isolate or not:**|Select whether to isolate the service port from the management port:     -   **Yes**: This port can only be used as a local Web management port and cannot be used as a service port.

In the isolation mode, the service traffic and the management traffic do not communicate with each other, achieving a high level of security.

    -   **No**: This port is used as both the local Web management port and the service port.
 |
    |**Management port IP:**|The management IP address is used for Web access of the local client.|
    |**Next Hop:**|If you choose to isolate the service port from the management port, specify the next hop of the management port.|

    ![Service IP management](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40456/156687189521111_en-US.png)


## Step 4: Configure ports and routes {#section_6g3_yhb_ufb .section}

There are six ports on an SAG-1000 device. Port 0 and Port 1 are SFP optical ports, and Port 2 to Port 5 are RJ45 electrical ports. You can configure a static route or Open Shortest Path First \(OSPF\) routes for port connection.

1.  Log on to the Web console of the SAG device and on the Configuration page, click **Port Management**.
2.  Configure the ports of the SAG device according to the following information, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Connection Type**|Select whether to access the switch by using static routes or dynamic routes. **Note:** When dual-device one-arm mode is used, only dynamic routing is supported.

 |
    |**Port**|Click **Edit** in the **Configurations** section, enter the IP address of the port used for communication and select whether to enable OSPF. Port 2 is the default management port.

 |
    |OSPF routing configuration|
    |**Area ID**|The ID of the area. Make sure that area IDs of SAG device 1 and SAG device 2 are different and the area ID of each SAG device is the same as that of the corresponding peer switch.

 |
    |**Hello\_time**|The interval in which hello is sent. Unit: seconds. Default value: 3.

 |
    |**Dead\_time**|The dead interval of OSPF neighbor. Unit: seconds. The neighbor relation stops if no hello packet is received during the dead time. Default value: 10.

 |
    |**Authentication Method**|Select an authentication method.     -   **Not**: Do not perform authentication.
    -   **Plain Text**: Enter a clear text password.
    -   **MD5**: Use the MD5 method to perform authentication. Enter the MD5 key ID and the MD5 key.
 |
    |**Routerid**|The ID of the OSPF router. We recommend that you directly use the service IP address.|
    |**Area Type**|The area type is nssa by default.|


