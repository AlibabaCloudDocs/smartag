# Flow log overview {#concept_1829996 .concept}

This topic provides an overview of the flow log function of Smart Access Gateway \(SAG\). A flow log is used to capture the traffic data of SAG instances. After you enable the flow log function, you can use the data aggregated in flow logs to monitor traffic flows, troubleshoot network faults, analyze service trends, and optimize your services.

**Note:** The flow log function is supported only by the SAG-1000 device.

## Background information {#section_cjy_i8l_qd2 .section}

You can specify the SAG instances of which the traffic data you want to capture. The following flow logs can be used to store captured data:

-   SLS flow logs: The captured traffic data is stored in Alibaba Cloud Log Service.
-   NetFlow flow logs: The captured traffic data is stored in your NetFlow server.

SLS flow logs store the captured traffic data in Alibaba Cloud Log Service, where you can view and analyze the traffic data. The SLS flow log function is currently in the beta testing phase. During this phase, you are only charged for the storage and retrieval of traffic data in Log Service.

The traffic data captured by the SLS flow log function is written to Log Service as flow log records. Each flow log record captures specified traffic data in a specified capture window. During this period, data is aggregated and then released to the flow log record.

NetFlow flow logs encapsulate the captured traffic data into NetFlow packets based on the NetFlow protocol and then transmit the packets to your NetFlow server, where you can view and analyze the traffic data.

The following table describes the fields of a flow log record.

|Field|Description|
|:----|:----------|
|Instance\_id|The ID of the SAG instance. **Note:** This field is not supported by NetFlow flow logs.

 |
|snid|The SN of the SAG instance. **Note:** This field is not supported by NetFlow flow logs.

 |
|ali-uid|The account ID. **Note:** This field is not supported by NetFlow flow logs.

 |
|start|The start time of the capture window.|
|end|The end time of the capture window.|
|protocol|The protocol type of the traffic.|
|srcaddr|The source IP address.|
|srcport|The source port.|
|dstaddr|The destination IP address.|
|dstport|The destination port.|
|packets|The number of data packets.|
|BYTES|The size of data packets.|
|tcp-flags|The TCP flag.|
|tos|The IP header field ToS.|
|inport|The ID of the incoming port, that is, the ID of the interface where traffic comes in.|
|outport|The ID of the outgoing port, that is, the ID of the interface where traffic comes out.|

## Configuration process {#section_5v8_ym1_22r .section}

The following figure shows the process of configuring the flow log function.

![Flow log configuration process](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1448964/156879569457129_en-US.png)

1.  Create a flow log.

    You can choose to create an SLS flow log or a NetFlow flow log by selecting the storage location of the flow log. For more information, see [Create a flow log](intl.en-US/Flow log/Create a flow log.md#).

2.  Associate the flow log with an SAG instance.

    To record the traffic data of an SAG instance, you must associate a flow log with the SAG instance after you create the flow log, For more information, see.[Associate an SAG instance](intl.en-US/Flow log/Associate an SAG instance.md#)

3.  View the flow log.

    After associating the flow log with an SAG instance, you can view the flow log. By analyzing the captured traffic data in the flow log, you can monitor the traffic flows, optimize costs, and troubleshoot network faults. For more information, see [View a flow log](intl.en-US/Flow log/View a flow log.md#).


