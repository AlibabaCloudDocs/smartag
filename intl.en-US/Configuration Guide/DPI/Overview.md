---
keyword: [DPI, application-aware QoS policies, application-aware ACLs, view traffic monitoring data of applications]
---

# Overview

Smart Access Gateway \(SAG\) supports the deep packet inspection \(DPI\) feature. The DPI feature allows you to create application-aware quality of service \(QoS\) policies and access control lists \(ACLs\) and view monitoring data of applications. This feature regulates network traffic routes through simple and effective solutions and analyzes traffic distribution to provide a better user experience.

## Introduction to DPI

DPI retrieves the payload of data packets to identify and re-organize the application data transmitted through the application layer. This allows DPI to gain full insights into an application and filter data packets based on system control policies. In addition, the system can display the distribution of network traffic based on the application data collected by DPI.

DPI supports the following features:

-   Application-aware QoS policies
-   Application-aware ACLs
-   Traffic monitoring based on applications

When you create a QoS policy or an ACL, you must specify an application. DPI identifies and analyzes network traffic based on the specified application and performs operations based on system control policies. You can choose one of the following methods to specify applications:

-   Specify applications: DPI identifies each application. When you create a policy, you can specify an application.
-   Specify application groups: DPI classifies applications into groups based on the application characteristics. When you create a policy, you can specify an application group. After you specify an application group, the policy applies to all applications in the group.

## Procedure for using DPI

The DPI feature is disabled by default. You must enable and configure the DPI feature before you can use it.

**Note:** The following SAG device models support the DPI feature: SAG-1000 and SAG-100WM.

1.  Enable the DPI feature. For more information, see [Manage DPI]().
2.  Create a policy based on your business requirements.
    -   Create an application-aware QoS policy. For more information, see [What is a QoS policy?](/intl.en-US/Configuration Guide/QoS policies/Overview.md).
    -   Create an application-aware ACL. For more information, see [Overview](/intl.en-US/Configuration Guide/Access control/Overview.md).
    -   View monitoring data of applications. For more information, see [View traffic monitoring data of applications]().

        **Note:** You must enable the DPI-based monitoring feature for the SAG instance before you can view the traffic monitoring data. For more information, see [Manage DPI]().


