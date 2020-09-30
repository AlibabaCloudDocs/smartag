# Authorize cross-account association

You can authorize another Alibaba Cloud account to associate its Cloud Connect Network \(CCN\) instances or virtual border routers \(VBRs\) with Smart Access Gateway \(SAG\) instances under your account.

The UID of the peer account and the ID of the CCN instance or VBR are obtained.

1.  Log on to the [Smart Access Gateway console](https://smartag.console.aliyun.com).

2.  Use one of the following methods to open the Network Configuration tab.

    -   Click the ID of the target SAG instance. On the instance details page, click the **Network Configuration** tab.
    -   Find the target SAG instance and click **Network Configuration** in the **Actions** column.
3.  In the left-side navigation tree, click **Network Instance Details**.

4.  In the Authorized Cross-account Instances section, click **Authorize CCN Instance**.

5.  In the Authorize CCN Instance dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Authorized Account UID**|Enter the UID of the account that you want to authorize, for example, 168840159596\*\*\*\*.|
    |**Network Type**|Select the type of connection that is allowed to be established between your account and the peer account. Valid values:     -   **Cloud Connect Network**: If you select this option, you must specify the ID of the CCN instance that is under the peer account.
    -   **Virtual Border Router**: If you select this option, you must specify the ID of the VBR that is under the peer account. |
    |**Target CCN Instance ID**|Enter the ID of the peer CCN instance, for example, ccn-6dhj3m2fz7p6og\*\*\*\*.|
    |**Peer VBR ID**|Enter the ID of the peer VBR, for example, vbr-o6w14e21pzziti4tp\*\*\*\*.|


