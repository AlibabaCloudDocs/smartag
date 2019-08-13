# Add a DNAT entry {#task_1012677 .task}

This topic describes how to add a DNAT entry to a Smart Access Gateway \(SAG\) instance to enable the DNAT function. By using the DNAT function, you can forward requests received by public IP addresses to Alibaba Cloud instances according to custom mapping rules.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).
2.  In the left-side navigation pane, click **Smart Access Gateway**, and then click the target instance ID or click **Configure Network** in the **Actions** column.
3.  On the SAG instance details page, click **DNAT**.
4.  On the DNAT tab page, click **Add DNAT**.
5.  In the Add DNAT Rule dialog box, configure the mapping rules. 

    The following table describes the DNAT rule parameters.

    |Parameter|Description|
    |---------|-----------|
    |Connection Type|Select the DNAT mapping method. Options:     -   **All Ports**: IP mapping, which associates an EIP with the target ECS instance. If this method is used, all requests destined for the specified public IP address are forwarded to the target ECS instance.
    -   **Specified Port**: port mapping. If this method is used, the NAT Gateway forwards the requests from the specified protocol and port to the specified port of the target ECS instance.

If you select this method, you must also specify the corresponding public port, internal port, and protocol.

 |
    |Public IP Address|Enter a public IP address. **Note:** A public IP address that is already used in a SNAT entry cannot be used to create a DNAT entry.

 |
    |Internal IP Address|Enter the private IP address of the ECS instance that will use the DNAT entry to access the Internet.|
    |Public Port|The external port for traffic forwarding.|
    |Internal Port|The internal port for traffic forwarding.|
    |Protocol|The protocol type of the forwarding port.|

6.  Click **OK**.

