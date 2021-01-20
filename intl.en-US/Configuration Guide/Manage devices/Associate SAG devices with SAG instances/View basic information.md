# View basic information

After you purchase a Smart Access Gateway \(SAG\) device, the system creates an SAG instance that allows you to manage the SAG device. This topic describes how to view basic information about an SAG device through the SAG instance.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  On the Smart Access Gateway page, click the ID of a target SAG instance. On the **Basic Information** tab, you can view the basic information about the SAG device. The following table lists the basic information.

    |Parameter|Description|
    |---------|-----------|
    |**SAG instance ID**|The ID of the SAG instance.|
    |**SAG Instance Name**|The name of the SAG instance.You can click **Edit** to modify the name.

The name must be 2 to 100 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character. |
    |**Description**|The description of the SAG instance.You can click **Edit** to modify the description.

The description must be 2 to 256 characters in length and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter or a Chinese character. |
    |**WAN Upstream Bandwidth**|The maximum upstream bandwidth of the SAG device when the SAG device is connected to the Internet through a WAN port. Unit: Mbit/s.You can click **Edit** to modify the maximum upstream bandwidth. |
    |**4G Upstream Bandwidth**|The maximum upstream bandwidth of the SAG device when the SAG device is connected to the Internet through 4G networks. Unit: Mbit/s.You can click **Edit** to modify the maximum upstream bandwidth. |
    |**Method to Synchronize with On-premises Routes**|The method that the SAG device uses to synchronize Alibaba Cloud-facing routes. For more information, see [Advertise routes to Alibaba Cloud](/intl.en-US/Configuration Guide/Configure networks in the cloud/Advertise routes to Alibaba Cloud.md).|
    |**ACL**|The access control list \(ACL\) instance that is associated with the SAG instance. For more information, see [Overview](/intl.en-US/Configuration Guide/Access control/Overview.md).|
    |**Transmission Optimization**|Specifies whether transmission optimization is enabled.Transmission optimization uses forward error correction \(FEC\) to minimize packet loss. This makes data transmission more reliable.

To enable transmission optimization, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308). |
    |**Controller Status**|The status of the SAG device.    -   Order Placed: The order of the SAG device has been placed and the package has not been dispatched.
    -   Order Shipped: The package has been dispatched. After you receive the package, sign for it.
    -   Not Associated with CCN: The SAG instance is not associated with a Cloud Connect Network \(CCN\) instance or virtual boarder router \(VBR\).
    -   Disconnected: The SAG device is not connected to Alibaba Cloud.
    -   Ready: The SAG device is working as expected.
    -   Overdue Payment: The SAG device is unavailable due to overdue payments. |
    |**VPN Status**|The status of the VPN connection through which the SAG device is connected to Alibaba Cloud.    -   Normal: The VPN connection is working as expected.

If the VPN connection is working as expected, you can place the pointer over **Normal** to view the protocol that the VPN connection uses, including:

        -   ipsecVPN: uses Internet Protocol Security \(IPsec\). By default, the SAG device uses IPsec to establish the VPN connection.
        -   aliVPN: uses the Transmission Control Protocol \(TCP\) and User Datagram Protocol \(UDP\) to provide an enhanced VPN connection, encapsulate data packets on any port, minimize packet loss, and improve data transmission efficiency.

To enable aliVPN, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308).

    -   Abnormal: The VPN connection is not working as expected. |
    |**Created At**|The time when the SAG instance was created.|
    |**Expires At**|The date when the SAG instance expires.|
    |**Device Type**|The type of the SAG device that is associated with the SAG instance.|
    |**QoS**|The Quality of Service \(QoS\) instance that is associated with the SAG instance. For more information, see [What is a QoS policy?](/intl.en-US/Configuration Guide/QoS policies/Overview.md).|
    |**Flow Log**|The flow log instance that is associated with the SAG instance. For more information, see [Overview](/intl.en-US/Configuration Guide/Flow logs/Overview.md).|


