# Create an ACL rule

Smart Access Gateway \(SAG\) allows you to create access control list \(ACL\) rules for a specific SAG instance. An ACL rule contains IP addresses that are allowed or forbidden to access the Internet or private network.

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the left-side navigation pane, click **ACL**.

3.  On the ACL page, click **Create ACL**.

    ![Add ACL](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1080287951/p132918.png)

4.  In the Create ACL dialog box that appears, specify the list name and click **OK**. You are redirected to the ACL page.

    The name must be 2 to 100 characters in length and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character.

5.  Click the ID of the target ACL to go to the details page. Alternatively, find the target ACL and click **Configure Rules** in the **Actions** column.

    ![Add rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1080287951/p132917.png)

6.  Click **Add Rule** and set the following parameters to create an ACL rule.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Name**|Specify a name for the rule. The name must be 2 to 100 characters in length and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter or Chinese character. |
    |**Network Type**|    -   **Private Network**: The rule controls network traffic originated from and destined for private IP addresses.
    -   **Public Network**: The rule controls network traffic originated from and destined for the Internet. |
    |**Rule Direction**|    -   **Outbound**: The rule controls outbound network traffic of the private network that is associated with the SAG instance.
    -   **Inbound**: The rule controls inbound network traffic of the private network that is associated with the SAG instance. |
    |**Policy**|Supports **Allow** or **Block**.|
    |**Protocol**|Select the protocol to which the rule applies.|
    |**Source CIDR Block**|    -   For outbound traffic: Enter the source CIDR block from which requests are transmitted from the private network.
    -   For inbound traffic: Enter the source CIDR block from which requests are transmitted to the private network. |
    |**Source Port Range**|Specify the range of the source ports. Valid formats: 1/200 and 80/80. Enter -1/-1 to specify all ports.    -   If TCP or UDP is selected, specify source ports from 1 to 65535.
    -   If ICMP is selected, set the source port range to -1/-1.
    -   If All is selected, set the source port range to -1/-1. |
    |**Destination CIDR Block**|    -   For outbound traffic: Enter the destination CIDR block to which requests are transmitted.
    -   For inbound traffic: Enter the destination CIDR block of the private network to which requests are transmitted. |
    |**Destination Port Range**|Specify the range of the destination ports. Valid formats: 1/200 and 80/80. Enter -1/-1 to specify all ports.    -   If TCP or UDP is used, specify the source ports from 1 to 65535.
    -   If ICMP is used, set the destination port range to -1/-1.
    -   If All is selected, set the destination port range to -1/-1. |
    |**Priority**|Valid values: 1 to 100. A smaller value represents a higher priority. If rules assigned the same priority, the rule whichever applied first prevails.|

7.  Click **OK**.

8.  After you add the rule, navigate to the **Associated Instances** tab and click **Associate with Instance** to select an SAG instance to which the rule applies.

    ![ACL SAG](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1080287951/p132916.png)

9.  Click **OK**.


