# Authorize cross-account association

You can authorize another Alibaba Cloud account to associate its Cloud Connect Network \(CCN\) instances or virtual border routers \(VBRs\) with Smart Access Gateway \(SAG\) instances under your account.

The UID of the peer account and the ID of the CCN instance or VBR are obtained.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  In the top menu bar, select the region.

3.  In the left-side navigation pane, click **Smart Access Gateway**.

4.  On the Smart Access Gateway page, find the SAG instance.

5.  Use one of the following methods to go to the Network Configuration tab of the SAG instance:

    -   Click the ID of the SAG instance. On the instance details page, click the **Network Configuration** tab.
    -   Find the SAG instance and click **Network Configuration** in the **Actions** column.
6.  In the left-side navigation tree, click **Network Instance Details**.

7.  In the Authorized Cross-account Instances section, click **Authorize CCN Instance**.

8.  In the Authorize CCN Instance dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Authorized Account UID**|Enter the UID of the account that you want to authorize, for example, 168840159596\*\*\*\*.|
    |**Network Type**|Select the type of connection that is allowed to be established between your account and the peer account. Valid values:     -   **Cloud Connect Network**: If you select this option, you must specify the ID of the CCN instance that is under the peer account.
    -   **Virtual Border Router**: If you select this option, you must specify the ID of the VBR that is under the peer account. |
    |**Target CCN Instance ID**|Enter the ID of the peer CCN instance, for example, ccn-6dhj3m2fz7p6og\*\*\*\*.|
    |**Peer VBR ID**|Enter the ID of the peer VBR, for example, vbr-o6w14e21pzziti4tp\*\*\*\*.|


**Related topics**  


[GrantSagInstanceToVbr](/intl.en-US/API Reference/SAG instances/GrantSagInstanceToVbr.md)

[GrantSagInstanceToCcn](/intl.en-US/API Reference/SAG instances/GrantSagInstanceToCcn.md)

