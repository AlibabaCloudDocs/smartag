# Configure an access control list {#task_ffn_pvj_dhb .task}

This topic describes how to configure an access control list \(ACL\) rule for a target Smart Access Gateway instance to permit or deny access to or from specified IP addresses in the ACL rule.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **ACL**.
3.  On the ACL page, click **Create ACL**.
4.  Configure the name of the ACL, and then return to the ACL page. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40706/156527676740769_en-US.png)

5.  Click the ID of the ACL instance or **Configure Rules** in the **Actions** column.
6.  In the left-side navigation pane, click **ACL Rules** and then click **Add Rule** to add an ACL rule to the ACL instance. 

    |Configuration|Description|
    |-------------|-----------|
    |**Direction**|     -   **Outbound**: Traffic from the local branch connected to Smart Access Gateway to the external environment.
    -   **Inbound**: Traffic from the external environment to the local branch connected to Smart Access Gateway.
 |
    |**Authorization Policy**|Select **Allow** or **Refuse**.|
    |**Protocol**|The transport layer protocol.|
    |**Source CIDR**|     -   **Outbound**: The CIDR block of the local branch that initiates access.
    -   **Inbound**: The CIDR block that accesses the local branch.
 |
    |**Source Port Range**|The source port range of the transport layer.     -   TCP/UDP protocol: \[1, 65535\]
    -   ICMP protocol: -1/-1
    -   All: -1/-1
 |
    |**Destination CIDR:**|     -   **Outbound**: The external destination CIDR block to be accessed.
    -   **Inbound**: The destination CIDR block of the local branch to access.
 |
    |**Destination Port Range**|The destination port range of the transport layer.     -   TCP/UDP protocol: \[1, 65535\]
    -   ICMP protocol: -1/-1
    -   All: -1/-1
 |
    |**Priority**|Valid range: 1–100. The smaller the number, the higher the priority. If the priority of two rules is the same, the rule added earlier takes effect.|

7.  Click **OK**.
8.  After the ACL rule is configured, click **Add Instances** in the **Actions** column to add Smart Access Gateway instances that use the ACL rule. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40706/156527676741272_en-US.png)

9.  Click **Save**. To remove an instance, click the target instance and then click **Remove** in the **Actions** column.

