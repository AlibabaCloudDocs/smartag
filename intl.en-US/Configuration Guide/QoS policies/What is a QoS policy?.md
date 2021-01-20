---
keyword: [QoS policy, application-aware QoS policy, ensure service bandwidth]
---

# What is a QoS policy?

Smart Access Gateway \(SAG\) supports quality of service \(QoS\) policies. QoS policies classify network traffic distributed across applications and services. You can use QoS policies to allocate bandwidth resources base on business requirements and improve network quality.

## Features

QoS policies can be used to reduce network latency and network congestion. You can apply a QoS policy to an SAG instance to allocate bandwidth resources based on business requirements, reduce network latency, and improve network resource usage.

A QoS policy consists of one or more traffic throttling rules. A traffic throttling rule consists of one or more traffic classification rules. A QoS policy classifies network traffic based on the traffic classification rules and allocates bandwidth resources based on the priorities of the traffic throttling rules.

You can use the following methods to create a QoS policy:

-   Create a 5-tuple

    A 5-tuple includes the following tuples:

    -   Protocol: The protocol of the data packets. The supported protocols provided in this topic are for reference only. The actual supported protocols in the console shall prevail.
    -   Source CIDR block: The source CIDR block from which the data packets are sent.
    -   Destination CIDR block: The destination CIDR block to which the data packets are sent.
    -   Source port: The source port from which the data packets are sent.
    -   Destination port: The destination port to which the data packets are sent.
-   Create an application-aware classification rule

    QoS policies can use the deep packet inspection \(DPI\) feature to classify network traffic based on an application or an application group. The supported applications and application groups provided in this topic are for reference only. The actual supported applications and application groups in the console shall prevail.

    **Note:** To classify network traffic based on applications or application groups, you must enable the DPI feature first. Only SAG instances that have the DPI feature enabled support application-aware classification rules. For more information about how to enable the DPI feature, see [Manage DPI](/intl.en-US/Configuration Guide/DPI/Manage DPI.md). For more information about the DPI feature, see [Overview](/intl.en-US/Configuration Guide/DPI/Overview.md).


## Procedure for using a QoS policy

1.  Create a QoS policy.

    Create traffic throttling rules and traffic classification rules for the QoS policy. For more information, see [Manage QoS policies](/intl.en-US/Configuration Guide/QoS policies/Create a QoS policy.md).

2.  Apply the QoS policy to an SAG instance.

    Apply the QoS policy to an SAG instance. For more information, see [Associate with or disassociate from an SAG instance](/intl.en-US/Configuration Guide/QoS policies/Apply a QoS policy to an SAG instance.md).


## Limits

-   QoS policies applied to SAG instances can throttle only outbound traffic.
-   When you create a 5-tuple, make sure that the settings of the tuples do not overlap with each other.
-   When you create a QoS policy that throttles traffic based on a specific bandwidth range, the system does not check whether the minimum and maximum bandwidth values specified in the policy meet the bandwidth requirements of the SAG instances to which the policy applies.

## Limits

|Resource|Default limit|Quota increase|
|--------|-------------|--------------|
|The maximum number of QoS policies that can be applied to an SAG instance|1|N/A|
|The maximum number of traffic throttling rules that can be created in a QoS policy|3|[Submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)A QoS policy supports at most four traffic throttling rules. |
|The maximum number of QoS policies that can be created under an Alibaba Cloud account|10|[Submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)|
|The maximum number of traffic classification rules that can be created for a traffic throttling rule|50|[Submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)|

