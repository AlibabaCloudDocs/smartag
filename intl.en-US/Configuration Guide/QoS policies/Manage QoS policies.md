# Manage QoS policies

This topic describes how to create or delete a quality of service \(QoS\) policy.

## Create a QoS policy

Create a QoS policy that consists of traffic throttling rules and traffic classification rules. Then, Smart Access Gateway \(SAG\) classifies network traffic and allocates bandwidth resources based on these rules.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  In the left-side navigation pane, click **QoS Policy**.

4.  On the QoS Policy page, click **Create QoS Policy**.

5.  On the Create QoS Policy page, specify a name for the policy and create a throttling rule and a classification rule.

    |Section|Parameter|Description|
    |-------|---------|-----------|
    |**Basic Information**|**QoS Policy Name**|Specify a name for the QoS policy.The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter. |
    |**QoS Policy Description**|Enter a description for the QoS policy.The description must be 2 to 100 characters in length, and can contain digits, periods \(.\), hyphens \(-\), and underscores \(\_\). It must start with a letter. |
    |**Rule**|**Rule Priority**|Specify a priority for the rule. If bandwidth resources are insufficient during data transmission, bandwidth resources are allocates based on the priorities of the throttling rules.

Valid values are from 1 to 3. A smaller value represents a higher priority.

**Note:** To set the priority to 4, you must [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308). |
    |**Throttling Policy**|You can select one of the following options to create a throttling rule:     -   **By Percentage**: ensures that the percentage of bandwidth resources allocated for the specified type of service is not lower than the specified percentage.

If you select **By Percentage**, you must select the bandwidth type and set the minimum and maximum percentages. SAG supports the following bandwidth types:

        -   **CCN Bandwidth**: The bandwidth resources used to transfer data from the on-premises network to Alibaba Cloud.
        -   **Total Internet Bandwidth**: The bandwidth resources used to transfer data from the on-premises network to the Internet.
For example, the bandwidth used to transfer data from the on-premises network to the Internet is 20 Mbit/s, and the bandwidth resources required for transferring audio data to the Internet is from 10 to 15 Mbit/s. In this case, you can select **Total Internet Bandwidth** and create a 5-tuple. In the 5-tuple, set the minimum percentage to 50% and the maximum to 75%.

    -   **By Bandwidth**: specifies the minimum and maximum bandwidth values for a specified type of service. |
    |**Traffic Classification Rule**|**5-Tuple Name**|Specify a name for the 5-tuple. The name must be 2 to 100 characters in length, and can contain digits, hyphens \(-\), and underscores \(\_\). It must start with a letter. |
    |**5-Tuple Description**|Enter a description of the 5-tuple. The description must be 1 to 512 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**Protocol**|Specify the protocol of the data packets.The supported protocols provided in this topic are for reference only. The actual supported protocols in the console shall prevail. |
    |**Source CIDR Block**|Specify the source CIDR block from which the data packets are sent.|
    |**Source Port**|Specify the source port from which the data packets are sent. Valid values: 1 to 65535 and -1.

Set the source port range in one of the following formats: 1/200 and 80/80. A value of -1/-1 specifies all ports. |
    |**Destination CIDR Block**|Specify the destination CIDR block to which the data packets are sent.|
    |**Destination Port**|Specify the destination port to which the data packets are sent. Valid values: 1 to 65535 and -1.

Set the destination port range in one of the following formats: 1/200 and 80/80. A value of -1/-1 specifies all ports. |
    |**Effective Period**|Specify the beginning and end of the validity period of the 5-tuple.|
    |**Application Group**|Specify the application group to which the 5-tuple applies.An application group may contain multiple applications. After you specify an application group, the 5-tuple applies to all applications in the group.

The supported application groups provided in this topic are for reference only. The actual supported application groups in the console shall prevail. |
    |**Application**|Specify the application to which the 5-tuple applies.You can select an application from the specified application group.

The supported applications provided in this topic are for reference only. The actual supported applications in the console shall prevail. |

    **Note:**

    -   If you specify an **Application Group** or an **Application**, the QoS policy is an application-aware QoS policy. Application-aware QoS polices can be applied to only SAG instances that have the DPI feature enabled. For more information about how to enable the DPI feature, see [Manage DPI](/intl.en-US/Configuration Guide/DPI/Manage DPI.md).
    -   If you specify both an **Application Group** and an **Application**, the QoS policy is applied to all applications in the specified application group and the specified **Application**.
6.  Click **Create**.


## Delete a QoS policy

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the SAG instance is deployed.

3.  In the left-side navigation pane, click **QoS Policy**.

4.  On the QoS Policy page, find the QoS policy that you want to delete.

5.  Click **Delete** in the **Actions** column.

6.  In the **Delete QoS Policy** message, confirm the QoS policy and click **OK**.


**Related topics**  


[What is a QoS policy?](/intl.en-US/Configuration Guide/QoS policies/What is a QoS policy?.md)

