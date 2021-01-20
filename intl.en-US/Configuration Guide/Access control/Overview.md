---
keyword: [access control, application-aware access control, filter traffic]
---

# Overview

Smart Access Gateway \(SAG\) supports access control lists \(ACLs\). You can create an ACL to allow or deny specific data traffic to improve the security of your networks.

## Descriptions of ACLs

An ACL is used to filter traffic based on the specified ACL rule and action policy. An ACL rule consists of match conditions and the action policy:

-   Match condition: You can specify the following items as match conditions for an ACL rule: network type, rule direction, protocol type, source CIDR block, source port, destination CIDR block, destination port, application group, and application type. For more information, see [Manage ACL rules](/intl.en-US/Configuration Guide/Access control/Manage ACL rules.md).

    **Note:** Before you create an application-aware ACL rule, you must enable the deep packet inspection \(DPI\) feature. You can create application-aware ACL rules for only SAG instances that have DPI enabled. For more information about how to enable DPI, see [Manage DPI](/intl.en-US/Configuration Guide/DPI/Manage DPI.md). For more information about DPI, see [Overview](/intl.en-US/Configuration Guide/DPI/Overview.md).

-   Action policy: You can specify whether to allow or deny traffic that meets the ACL rule.

You can create one or more ACL rules for an ACL. By default, the system filters traffic based on ACL rules in descending order of rule priorities.

-   If traffic meets an ACL rule, the system allows or denies the traffic based on the specified action policy. In this case, the matching process ends immediately and the system stops comparing the traffic with another ACL rule.
-   If the traffic does not meet any ACL rule, the system allows the traffic by default.

## Procedure

1.  Create an ACL.

    For more information, see [Manage ACLs](/intl.en-US/Configuration Guide/Access control/Manage ACLs.md).

2.  Create ACL rules.

    For more information, see [Manage ACL rules](/intl.en-US/Configuration Guide/Access control/Manage ACL rules.md).

3.  Associate the ACL with an SAG instance.

    Associate the ACL with an SAG instance. For more information, see [Manage SAG instances associated with ACLs](/intl.en-US/Configuration Guide/Access control/Manage SAG instances associated with ACLs.md).


## Limits

|Item|Default limit|Quota increase|
|----|-------------|--------------|
|The maximum number of ACLs that can be associated with an SAG instance|1|N/A|
|The number of ACL rules that can be created for an ACL|50|[Submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)|
|The number of ACLs that can be created under an Alibaba Cloud account|10|[Submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.15120809.nav-right.dticket.130266ebEB92in#/ticket/add/?productId=1308)|

