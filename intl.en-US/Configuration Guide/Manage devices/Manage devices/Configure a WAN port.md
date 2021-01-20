# Configure a WAN port

A Wide Area Network \(WAN\) port can connect a private network to Alibaba Cloud. This topic describes how to configure a WAN port for a Smart Access Gateway \(SAG\) device in the SAG console.

The WAN ports of an SAG device support static IP addresses, dynamic IP addresses, and Point-to-Point Protocol over Ethernet \(PPPoE\). You can configure WAN ports to connect private networks to Alibaba Cloud. The WAN ports of SAG devices also support bandwidth throttling and quality of service \(QoS\) policies, which improve bandwidth usage. For more information about QoS policies, see [What is a QoS policy?](/intl.en-US/Configuration Guide/QoS policies/Overview.md).

An SAG device supports multiple WAN ports.

-   An SAG-1000 device uses port 5 as the WAN port by default. You can manually specify other ports as WAN ports on an SAG-1000 device. For more information, see [Assign a role to a port](/intl.en-US/Configuration Guide/Manage devices/Manage devices/Assign a role to a port.md).
-   The number of WAN ports supported by an SAG-100WM device is based on the device type. Type 2 devices support multiple WAN ports. Type 1 devices support only one WAN port. The exterior of Type 1 and Type 2 devices is different. For more information about Type 1 and Type 2 devices, see [Descriptions of SAG-100WM](/intl.en-US/Smart Access Gateway/SAG-100WM usage instructions/Descriptions of SAG-100WM.md).

After you configure multiple WAN ports for your SAG device, you can configure WAN failover or load balancing based on multiple WAN ports to improve the availability of your network.

The following table describes the features and control conditions of WAN ports.

|Feature|Control condition|Description|
|-------|-----------------|-----------|
|WAN failover for high network availability|**Priority**|If you have configured multiple WAN ports for an SAG device, you can set the priority of each WAN port.The port that has the highest priority is used as the active port. Ports that have lower priorities are used as standby ports. Network traffic that goes through the SAG device is forwarded through the active port. If the active port is down, network traffic is automatically switched to a standby port.

Valid values of the priority: **-1 and 1 to 50**. A smaller value represents a higher priority. A value of **-1** indicates that the port is not used to forward network traffic. |
|Load balancing|-   **Internet service provider \(ISP\)**
-   **Weight**

|If the WAN ports are assigned the same priority, you can specify an ISP and a weight for each WAN port. This way, network traffic is forwarded by the ports based on their ISPs and weights.SAG devices redirect network traffic to ISP lines based on the destination IP addresses of data packets.

If the WAN ports are assigned the same ISP or the SAG device cannot match the network traffic with an ISP, the system redirects the network traffic to different ISPs based on the weight of each WAN port.

**Note:**

-   You can specify an **ISP** for each WAN port only if the SAG instance is deployed in the mainland China area.
-   The WAN ports can be used to balance only the load of network traffic transmitted over public networks. |

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  On the Smart Access Gateway page, use one of the following methods to open the Device Management tab.

    -   Click the ID of the SAG instance. On the instance details page, click the **Device Management** tab.
    -   Find the SAG instance and choose **![The Hide/Show icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0213713061/p135154.png)** \> **Device Management** in the **Actions** column.
4.  On the Device Management tab, if you have active and standby SAG devices, click the serial number to select the SAG device that you want to manage.

5.  In the left-side device management pane, click **Manage WAN Ports**.

6.  In the SNAT Information section, click **Edit**, enable or disable SNAT, and then click **OK**.

    Source Network Address Translation \(SNAT\) can convert the private source IP address of a private network to a public address. Then, the private network can communicate with the Internet. In inline mode, your private network can communicate with the Internet through SAG devices after SNAT is enabled for the SAG devices. For more information about the inline mode, see [Deployment modes](/intl.en-US/Product Introduction/Network topology/Deployment modes.md).

7.  In the DNS information section, click **Edit**, enter a DNS server address, and then click **OK**.

    **Note:** By default, an SAG device uses the DNS server assigned by Alibaba Cloud. You can also enter a custom DNS server address.

    ![DNS](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4528765061/p77458.png)

8.  In the WAN-Wired section, find the port that you want to manage and click **Edit**.

9.  In the dialog box that appears, configure the WAN port and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Connection Type**|Select a connection type for the WAN port.SAG devices support the following connection types:

    -   **Static IP**: If the WAN port of the SAG device is connected to a port that uses a static IP address, we recommend that you select this option. The WAN port is assigned a static IP address to communicate with other networks. If you select this option, you must set the following parameters:
        -   **IP**: Enter the IP address of the WAN port.
        -   **Subnet Mask**: Enter the subnet mask of the WAN port IP address.
        -   **Gateway**: Enter the gateway IP address of the SAG device.

**Note:**

            -   Make sure that the specified IP addresses of the WAN port and peer port fall within the same CIDR block.
            -   After the preceding parameters are set, the SAG device generates a default route.
    -   **Dynamic IP**: If the WAN port of the SAG device is connected to a port whose IP address is dynamically assigned by the Dynamic Host Configuration Protocol \(DHCP\) server, we recommend that you select this option. The WAN port uses an IP address that is dynamically assigned by the DHCP server to communicate with other networks.
    -   **PPPoE**: If the WAN port of the SAG device is connected to networks through dial-up connections, we recommend that you select this option. You must enter the username and password of the PPPoE account provided by the Internet service provider \(ISP\).
        -   **Account**: Enter the username of the PPPoE account.

The username must be 6 to 30 characters in length, and can contain digits and letters.

        -   **Password**: Enter the password of the PPPoE account.

The password must be 6 to 30 characters in length, and can contain digits and letters. |
    |**Priority**|Set the priority of the WAN port.Valid values of the priority: **-1 and 1 to 50**. A smaller value represents a higher priority. A value of **-1** indicates that the port is not used to forward network traffic. |
    |**ISP**|Select an ISP for the WAN port.SAG devices support the following ISPs:

    -   **China Telecom**
    -   **China Mobile**
    -   **China Unicom**
    -   **Other** |
    |**Bandwidth**|Set a bandwidth cap for the WAN port. This increases bandwidth usage. Unit: Mbit/s.When you set the bandwidth cap, take note of the following rules:

    -   If you set a bandwidth cap for the WAN port, you cannot set the **WAN Upstream Bandwidth** or **Upstream Bandwidth of Cellular Port** parameter. For more information, see [View basic information](/intl.en-US/Configuration Guide/Manage devices/Associate SAG devices with SAG instances/View basic information.md).
    -   If you have configured multiple WAN ports for an SAG device and the SAG device are assigned a QoS policy, the QoS policy is applied based on the following rules:
        -   If the WAN ports are assigned different priorities, the QoS policy throttles network traffic based on the bandwidth of the active port.
        -   If the WAN ports are assigned the same priority, the QoS policy throttles network traffic based on the lowest bandwidth cap value of the WAN ports.
    -   If the bandwidth cap of the WAN port is set to 0, it indicates that traffic forwarding on the WN port is not throttled. |
    |**Weight**|Set a weight for the WAN port.Valid values: **1 to 100**. Default value: **100**.

The weight of each WAN port determines the amount of network traffic forwarded on each WAN port. For example, the weight of a WAN port is set to 50 and that of another is set to 100. The ratio of the weights of these two ports is 1:2. If the SAG devices receive three data packets, one packet is forwarded from the WAN port whose weight is 50 and two packets are forwarded from the WAN port whose weight is 100. |


**Related topics**  


[ModifySagWan](/intl.en-US/API Reference/Port configurations/ModifySagWan.md)

[ModifySagWanSnat](/intl.en-US/API Reference/Port configurations/ModifySagWanSnat.md)

[ModifySagUserDns](/intl.en-US/API Reference/SAG instances/ModifySagUserDns.md)

