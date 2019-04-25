# Configure an access control list {#task_ffn_pvj_dhb .task}

This topic describes how to configure an access control list \(ACL\) rule for a target Smart Access Gateway instance \(SmartAG\) to permit or deny access to or from the specified public or private network IP address entered in the ACL rule.

1.  Log on to the [Smart Access Gateway management console](https://smartag.console.aliyun.com/). 
2.  In the left-side navigation pane, click **ACL**. 
3.  Click **Create Access Control List**, and then set a name for the ACL \(in this example, the name is test\). 
4.  Then, return to the ACL page. 
5.  Click the target ACL instance ID or click **Configure Rule** in the **Actions** column on the right. 
6.  In the left-side navigation pane, select the target **ACL** and click **Add ACL Rule** to add an ACL rule to the ACL instance. Then, configure the rule according to the following information: 

    |Item|Description|
    |----|-----------|
    |**Rule Direction**|Select a rule direction.    -   **Out direction**: Refers to external traffic accessed internally from the local branch \(where the SmartAG instance is located\).
    -   **In direction**: Refers to internal traffic of the local branch \(where the SmartAG instance is located\) that is accessed from an external network.
|
    |**Authorization Policy**|Select **Allow** or **Deny**.|
    |**Potocol Type**|The specified protocol. Select TCP or UDP.|
    |**Source Network Segment**|The address segment by which access is initiated. Supported parameters include:    -   **Out direction**: The private network address segment where the local branch initiates access to an external network.
    -   **In direction**: The private network address segment that accepts access from an external network.
|
    |**Source Port Range**|The transport layer source port range. Supported values include:    -   TCP/UDP protocol value range: 1 to 65535
    -   ICMP protocol value: -1/-1
    -   All value: -1/-1
 |
    |**Destination Network Segment**|The address segment that is involved with receiving network communications. Supported parameters include:    -   **Out direction**: The external destination network segment to be accessed.
    -   **In direction**: The target network segment of the local branch to be accessed.
|
    |**Destination Port Range**|The destination port range of the transport layer.    -   TCP/UDP protocol value range: 1 to 65535
    -   ICMP ptotocol value: -1/-1
    -   All value: -1/-1
|
    |**Priority**|Value range: 1 to 100. A smaller value indicates a higher the priority. If the priority levels of two rules are the same, the rule created first takes effect.|

7.  Click **OK**. 
8.  Click **Add Instance** in the **Actions** column, and then add the target SmartAG instance that needs to comply with the created ACL rule. 
9.  Click **Save**. You can also click **Manage Instance** in the **Actions** column to add or remove SmartAG instances as needed.

