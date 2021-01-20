---
keyword: [create an ACL rule, modify an ACL rule, delete an ACL rule, ACL rules for applications]
---

# Manage ACL rules

Smart Access Gateway \(SAG\) implements access control based on access control list \(ACL\) rules. This topic describes how to create, modify, and delete an ACL rule.

An ACL rule consists of match conditions and an action policy.

-   Match conditions: ACL rules can filter network traffic by network type, rule direction, protocol, source CIDR block, source port, destination CIDR block, destination port, application group, and application type. You can set match conditions based on your business requirements.
-   Action policy: ACL rules can allow or block network traffic.

## Create an ACL rule

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the region where the ACL is deployed.

3.  In the left-side navigation pane, click **ACL**.

4.  On the ACL page, click the ID of the ACL that you want to manage.

5.  On the ACL instance details page, click **Add Rule**.

6.  In the **Add Rule** dialog box, set the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Name**|Specify a name for the ACL rule. The name must be 2 to 100 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). |
    |**Network Type**|    -   **Private Network**: The ACL rule controls network traffic originated from and destined for private IP addresses.
    -   **Public Network**: The ACL rule controls network traffic originated from and destined for public IP addresses. |
    |**Rule Direction**|    -   **Outbound**: The ACL rule controls outbound network traffic of the on-premises network that is associated with the SAG instance.
    -   **Inbound**: The ACL rule controls inbound network traffic of the on-premises network that is associated with the SAG instance. |
    |**Policy**|Select **Allow** or **Block** to allow or block network traffic.|
    |**Protocol**|Select the protocol to which the ACL rule applies.The supported protocols provided in this topic are for reference only. The actual protocols in the SAG console shall prevail. |
    |**Source CIDR Block**|    -   For outbound traffic: Enter the source CIDR block that initiates requests from the on-premises network.
    -   For inbound traffic: Enter the source CIDR block from which requests are sent to the on-premises network. |
    |**Source Port Range**|Specify the range of the source ports.Valid values: 1 to 65535 and -1.

Set the source port range in one of the following formats: 1/200, 80/80, and -1/-1. -1/-1 specifies all ports. |
    |**Destination CIDR Block**|    -   For outbound traffic: Enter the destination CIDR block to which requests are sent.
    -   For inbound traffic: Enter the destination CIDR block of the on-premises network to which requests are sent. |
    |**Destination Port Range**|Specify the range of the destination ports.Valid values: 1 to 65535 and -1.

Set the destination port range in one of the following formats: 1/200, 80/80, and -1/-1. -1/-1 specifies all ports. |
    |**Rule Priority**|Specify the priority of the ACL rule.Valid values: 1 to 100. A smaller value represents a higher priority. If rules have the same priority, whichever applied to the SAG devices earlier takes effect.

The system filters requests based on ACL rules in descending order of rule priorities. The system performs the action specified in the matched rule on the requests. Requests that do not match any rule are allowed by default. |
    |**Application Group**|Select an application group to which you want to apply the ACL rule.An application group may contain multiple applications. The ACL rule is applied to all applications in the selected application group.

The supported applications provided in this topic are for reference only. The actual applications in the SAG console shall prevail. |
    |**Application**|Select applications to which you want to apply the ACL rule.You can select an application from the specified application group.

The supported applications provided in this topic are for reference only. The actual applications in the SAG console shall prevail. |

    **Note:**

    -   After you select an **Application Group** or **Application**, the ACL rule is applied to the selected application group or application. Application-based ACL rules can be applied to only SAG instances that has deep packet inspection \(DPI\) enabled. For more information about how to enable DPI, see [Manage DPI](/intl.en-US/Configuration Guide/DPI/Manage DPI.md).
    -   When you create an ACL rule, if you select an **Application Group** and an **Application**, the rule is applied to all the applications in the selected application group and the selected **Application**.

## Modify an ACL rule

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the region where the ACL is deployed.

3.  In the left-side navigation pane, click **ACL**.

4.  On the ACL page, click the ID of the ACL that you want to manage.

5.  On the ACL instance details page, find the ACL rule that you want to modify.

6.  In the **Actions** column, click **Modify**.

7.  In the **Edit Rule** dialog box, modify the settings and click **OK**.

    For more information about the parameters, see [Create an ACL rule](#section_s3v_gsa_x1w).


## Delete an ACL rule

1.  Log on to the [SAG console](https://smartag.console.aliyun.com/).

2.  In the top navigation bar, select the region where the ACL is deployed.

3.  In the left-side navigation pane, click **ACL**.

4.  On the ACL page, click the ID of the ACL that you want to manage.

5.  On the ACL instance details page, find the ACL rule that you want to delete.

6.  In the **Actions** column, click **Delete**.

7.  In the **Delete Rule** message, click **OK**.


