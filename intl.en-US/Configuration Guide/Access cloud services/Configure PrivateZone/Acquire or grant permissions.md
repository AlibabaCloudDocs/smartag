# Acquire or grant permissions

If you want to access Alibaba Cloud DNS PrivateZone \(PrivateZone\) through your on-premises network, you must acquire or grant relevant permissions. Make sure that the on-premises network is associated with a Cloud Connect Network \(CCN\) instance that is attached to a Cloud Enterprise Network \(CEN\) instance.

## Scenario 1: All under the same account

If the CCN instance, CEN instance, and VPC for which PrivateZone is enabled are under the same account, you can click **Authorization** on the Private Zone tab to complete authorization.

**Note:** You need to confirm the authorization only when it is your first time configuring PrivateZone.

|Item|User ID \(UID\) of the account|
|----|------------------------------|
|CEN|111111|
|VPC|111111|
|CCN|111111|

After authorization is completed, the system automatically creates a Resource Access Management \(RAM\) role named **AliyunSmartAGAccessingPVTZRole**. You can view this role on the RAM Roles page of the [RAM console](https://ram.console.aliyun.com/roles).

![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9161434851/p38863.png)

## Scenario 2: CCN instance under a different account

If the CEN instance and VPC are under the same account but the CCN instance is under a different account, you must modify the authorization policy.

|Item|UID of the account|
|----|------------------|
|CEN|111111|
|VPC|111111|
|CCN|333333|

**Note:** You must perform the following operations with the account to which the VPC belongs.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).

2.  Click the ID of the CEN instance.

3.  Click **Private Zone**, and then click **Authorization** to complete authorization.

    **Note:** You need to confirm the authorization only when it is your first time configuring PrivateZone.

4.  Log on to the [RAM console](https://ram.console.aliyun.com/roles).

5.  In the left-side navigation pane, click **RAM Roles**.

6.  Enter **AliyunSmartAGAccessingPVTZRole** in the search box and click the name of the policy that appears.

7.  Click the Trust Policy Management tab, and then click **Edit Trust Policy**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9161434851/p38865.png)

8.  Add `UID of the CCN account@smartag.aliyuncs.com` to the Service field, and then click **OK**.


## Scenario 3: CEN instance under a different account

If the CCN instance and VPC are under the same account but the CEN instance is under a different account, you must create an authorization policy with the account to which the VPC belongs.

|Item|UID of the account|
|----|------------------|
|CEN|333333|
|VPC|111111|
|CCN|111111|

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with the account to which the VPC belongs.

2.  In the left-side navigation pane, click **RAM Roles**.

3.  Set the following parameters and click **OK**. For more information, see [Create a RAM role for a trusted Alibaba Cloud service](/intl.en-US/RAM Role Management/Create a RAM role/Create a RAM role for a trusted Alibaba Cloud service.md).

    -   **Trusted entity type**: Select **Alibaba Cloud Service**.
    -   **Role Type**: Select **Normal Service Role**.
    -   **RAM Role Name**: Enter **AliyunSmartAGAccessingPVTZRole**.
    -   **Select Trusted Service**: Select **Smart Access Gateway**.
    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3787705061/p60147.png)

4.  Click the name of the newly created RAM role.

5.  On the Permissions tab, click **Add Permissions**.

6.  Enter **pvtz** in the search box below **System Policy**, and then click **AliyunPvtzReadOnlyAccess** to add read-only permissions on PrivateZone. For more information, see [Grant permissions to a RAM role](/intl.en-US/RAM Role Management/Grant permissions to a RAM role.md).

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0862852061/p38429.png)

7.  After the authorization is completed, you can click Trust Policy Management to view authorization information.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3787705061/p60148.png)


## Scenario 4: All under different accounts

If the CCN instance, CEN instance, and VPC are under different accounts, you must perform the following operations:

|Item|UID of the account|
|----|------------------|
|CEN|111111|
|VPC|222222|
|CCN|333333|

1.  Refer to Scenario 3 and create a RAM role with the account to which the VPC belongs.

    For more information, see [Scenario 3: CEN instance under a different account](#section_pil_zh5_23b).

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9727325061/p60149.png)

2.  Refer to Scenario 2 and add `UID of the CCN account@aliyuncs.com` to an existing policy with the account to which the VPC belongs.

    For more information, see [Scenario 2: CCN instance under a different account](#section_8m7_zgv_bbw).

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0261434851/p38427.png)


If you have multiple CCN instances and each CCN instance is under a different account, only add the CCN instances that require access to PrivateZone.

|Item|UID of the account|
|----|------------------|
|CEN|111111|
|VPC|222222|
|CCN|333333|
|CCN|444444|
|CCN|555555|

![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0261434851/p38431.png)

