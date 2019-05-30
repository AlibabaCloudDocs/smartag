# Configure ACL \(optional\) {#task_kl2_ndg_qfb .task}

You can add ACL rules to a Smart Access Gateway instance to allow or deny access from IP addresses in the ACL rules to the Internet or intranet.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com/).
2.  In the left-side navigation pane, click **ACL**.
3.  On the ACL page, click **Create ACL**.
4.  Configure the name of the ACL, and then return to the ACL page.
5.  Click the ID of the ACL instance or **Configure Rule** in the **Actions** column.
6.  In the left-side navigation pane, click **ACL Rule** and then click **Add ACL Rule** to add an ACL rule to the ACL instance. 

    |Configuration|Description|
    |-------------|-----------|
    |**Rule direction**|     -   **Outbound**: Traffic from the local branch connected to Smart Access Gateway to the external environment.
    -   **Inbound**: Traffic from the external environment to the local branch connected to Smart Access Gateway.
 |
    |**Authorization policy**|Select **Allow** or **Refuse**.|
    |**Protocol type**|The transport layer protocol.|
    |**Source address**|     -   **Outbound**: The CIDR block of the local branch that initiates access.
    -   **Inbound**: The CIDR block that accesses the local branch.
 |
    |**Source port**|The source port range of the transport layer. 0/65535 represents all ports.|
    |**Destination address**|     -   **Outbound**: The external destination CIDR block to be accessed.
    -   **Inbound**: The destination CIDR block of the local branch to access.
 |
    |**Destination port**|The destination port range of the transport layer. 0/65535 represents all ports.|
    |**Priority**|Valid range: 1–100. The smaller the number, the higher the priority. If the priority of two rules is the same, the rule added earlier takes effect.|

7.  Click **OK**.
8.  After the ACL rule is configured, click **Add Instance** in the **Actions** column to add Smart Access Gateway instances that use the ACL rule.

