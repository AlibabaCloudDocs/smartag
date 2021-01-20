# Create a QoS policy

This topic describes how to create a quality of service \(QoS\) policy. A QoS policy consists of priorities set for different types of packets, traffic throttling policies, and 5-tuples \(source IP address, destination IP address, source port, destination port, and protocol\).

1.  Log on to the [Smart Access Gateway \(SAG\) console](https://smartag.console.aliyun.com).

2.  In the left-side navigation pane, click **QoS Policy**.

3.  On the QoS Policy page, click **Create QoS Policy**.

4.  On the Create QoS Policy page, specify the policy name and configure one or more traffic throttling policies.

    Set the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Basic Information**|
    |**QoS Policy Name**|Specify a name for the QoS policy. The name must be 2 to 100 characters in length and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter. **Note:** You can create at most 10 QoS policies under each Alibaba Cloud account. To request a quota increase, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9). |
    |**QoS Policy Description**|Enter a description for the policy.|
    |**Rule** **Note:** You can create a maximum of three traffic throttling policies in each QoS policy. You can [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9) to increase the quota to seven at most. |
    |**Rule Priority**|Set a priority based on which bandwidth resources are allocated to different types of packet. Valid values are from 1 to 3. A larger value represents a higher priority. |
    |**Throttling Policy**|SAG supports the following types of traffic throttling policies.     -   **By Percentage**: throttles traffic based on the bandwidth percentage. You can specify the percentage of bandwidth resources guaranteed for a specific type of workload. This type of policy is suitable for scenarios where multiple stores use different amounts of bandwidth resources.

For example, if the maximum outbound bandwidth of the WAN port is 20 Mbit/s, you can set the maximum percentage to 95% and minimum to 20%.

    -   **By Bandwidth**: throttles traffic based on the bandwidth range. You can specify the minimum and maximum bandwidths guaranteed for different types of workloads based on their priorities.

Traffic is throttled based on the bandwidth, you do not need to specify the bandwidth type. |
    |**Traffic Classification Rule**: classifies traffic into different types based on the specified 5-tuples. A 5-tuple consists of the transport layer protocol, source CIDR block, destination CIDR block, source port, and destination port.|
    |**5-Tuple Name**|Specify a name for the 5-tuple. The name must be 2 to 100 characters in length, and can contain digits, hyphens \(-\), and underscores \(\_\). It must start with a letter or Chinese character.

 **Note:** You can add at most fifty 5-tuple rules to each QoS policy. To request a quota increase, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex?spm=a2c8b.12571063.console-base-top.dwork-order-1.6c3a5675P2NEW9). |
    |**5-Tuple Description \(Optional\)**|Enter a description for the 5-tuple. The description must be 1 to 512 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**Protocol**|Select a transport layer protocol for the 5-tuple.|
    |**Source CIDR Block**|Enter the source CIDR block from which requests are originated.|
    |**Source Port**|Enter the source ports from which requests are originated. Valid values: 1 to 65535 and -1.

 Set the source port range in one of the following formats: 1/200, 80/80, and -1/-1. -1/-1 specifies all ports. |
    |**Destination CIDR Block**|Enter the destination CIDR block for which requests are destined.|
    |**Destination Port**|Enter the destination port for which requests are destined. Valid values: 1 to 65535 and -1.

 Set the destination port range in one of the following formats: 1/200, 80/80, and -1/-1. -1/-1 specifies all ports. |
    |**Effective Period**|Specify the beginning and end of the validity period of the 5-tuple.|

5.  Click **Create**.


