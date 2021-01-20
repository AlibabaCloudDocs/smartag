---
keyword: check the status of a QoS rule
---

# Check the status of a QoS rule

After you create a quality of service \(QoS\) policy, you can check the status of its rules.

You must meet the following requirements before you can check the status of QoS rules:

-   A QoS policy is created. For more information, see [Manage QoS policies](/intl.en-US/Configuration Guide/QoS policies/Create a QoS policy.md).
-   The QoS policy is associated with a Smart Access Gateway \(SAG\) instance. For more information, see [Associate with or disassociate from an SAG instance](/intl.en-US/Configuration Guide/QoS policies/Apply a QoS policy to an SAG instance.md).

1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

2.  In the top navigation bar, select the region where the QoS policy is created.

3.  In the left-side navigation pane, click **QoS Policy**.

4.  On the **QoS Policy** page, find the QoS policy and check the status in the **Rule Status** column.

    -   **Functioning**: The QoS policy has been applied to the specified SAG devices.
    -   **Error**: One or more rules in the QoS policy failed to be applied to the specified SAG devices.

        You can click **Learn More** to view detailed information about the error.


