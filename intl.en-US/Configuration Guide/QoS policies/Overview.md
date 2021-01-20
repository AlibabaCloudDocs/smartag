# Overview

Smart Access Gateway \(SAG\) supports quality of service \(QoS\) policies that consist of 5-tuples \(source IP address, source port, destination IP address, destination port, and protocol\). You can create QoS policies to prioritize your workloads and allocate bandwidth resources based on the priority of the workloads.

QoS policies prioritize and allocate bandwidth resources for data transmission and reduce network latency, packet loss rates, and network jitter. This improves network performance.

If you have multiple stores that use different service systems such as enterprise resource planning \(ERP\), office automation \(OA\), and order management, these systems may compete for bandwidth resources. As a result, business-critical systems may have insufficient bandwidth resources, which causes packet loss.

SAG allows you to create QoS policies based on the requirements of different workloads to prioritize and allocate bandwidth resources. QoS policies help you improve the utilization of your network resources.

## Configuration procedure

The configuration procedure of QoS policies is:

1.  Create a QoS policy that throttles traffic based on the specified rules and classifies traffic based on the specified 5-tuples. For more information, see [t1861247.md\#](/intl.en-US/Configuration Guide/QoS policies/Create a QoS policy.md).
2.  Apply the QoS policy to an SAG instance. For more information, see [t1861256.md\#](/intl.en-US/Configuration Guide/QoS policies/Apply a QoS policy to an SAG instance.md).

## Limits on configurations

The limits on configuring QoS policies are:

-   QoS policies applied to SAG instances can throttle only outbound traffic.
-   5-tuples cannot overlap with each other.
-   When you create a QoS policy that throttles traffic based on a specific bandwidth range, the system does not check whether the minimum and maximum bandwidth specified in the policy meet the bandwidth requirements of the SAG instances to which the policy applies.

## Limits

The limits on using QoS policies are:

-   You can create at most 10 QoS policies under each Alibaba Cloud account.To request a quota increase, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308).
-   You can create at most fifty 5-tuples for each throttling rule.To request a quota increase, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308).
-   You can create at most three throttling rules for each QoS rule.You can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308) to increase the quota to at most seven.
-   You can associate an SAG instance with only one QoS policy, and this limit cannot be modified.

