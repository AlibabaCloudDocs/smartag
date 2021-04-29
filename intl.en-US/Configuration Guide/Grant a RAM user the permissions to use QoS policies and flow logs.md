# Grant a RAM user the permissions to use QoS policies and flow logs

This topic describes how to grant a RAM user the permissions to use quality of service \(QoS\) policies and flow logs.

1.  View the permission policies that have been attached to a RAM user.

    1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with your Alibaba Cloud account.

    2.  In the left-side navigation pane, choose **Permissions** \> **Grants**.

    3.  On the **Grants** page, find the RAM user that you want to manage and view the permission policies that have been attached.

        If the AliyunSmartAccessGatewayFullAccess permission policy is attached to the RAM user, the RAM user can use QoS policies and flow logs without other permissions. You can click **AliyunSmartAccessGatewayFullAccess** to view its details. The following code block shows the content of the AliyunSmartAccessGatewayFullAccess permission policy:

        ```
        {
            "Version": "1",
            "Statement": [
                {
                    "Action": "smartag:*",
                    "Resource": "*",
                    "Effect": "Allow"
                }
            ]
        }
        ```

2.  If the AliyunSmartAccessGatewayFullAccess permission policy is not attached to the RAM user, you can create a custom permission and attach it to the RAM user. This grants the RAM user the required permissions.

    If the RAM user needs to use QoS policies and flow logs, perform the following steps to create and attach a custom permission policy to the RAM user.

    1.  Log on to the [RAM console](https://ram.console.aliyun.com/).

    2.  In the left-side navigation pane, choose **Permissions** \> **Policies**.

    3.  On the **Policies** page, click **Create Policy**.

    4.  On the **Create Custom Policy** page, set the following parameters and click **OK**.

        -   **Policy Name**: Enter a name for the custom permission.
        -   **Configuration Mode**: Select a configuration mode. Select **Script**.
        -   **Policy Document**: Enter the content.
            -   QoS policies

                ```
                {
                    "Version": "1",
                    "Statement": [
                        {
                            "Action": [
                                "smartag:AssociateQos",
                                "smartag:CreateQos",
                                "smartag:CreateQosCar",
                                "smartag:CreateQosPolicy",
                                "smartag:DeleteQosCar",
                                "smartag:DeleteQosPolicy",
                                "smartag:DescribeQosCars",
                                "smartag:DescribeQosPolicies",
                                "smartag:DisassociateQos",
                                "smartag:GetQosAttribute",
                                "smartag:ModifyQos",
                                "smartag:ModifyQosCar",
                                "smartag:ModifyQosPolicy"
                            ],
                            "Resource": "*",
                            "Effect": "Allow"
                        }
                    ]
                }
                ```

            -   Flow logs

                ```
                {
                    "Version": "1",
                    "Statement": [
                        {
                            "Action": [
                                "smartag:ActiveFlowLog",
                                "smartag:AssociateFlowLog",
                                "smartag:CreateFlowLog",
                                "smartag:DeactiveFlowLog",
                                "smartag:DescribeFlowLogSags",
                                "smartag:DisassociateFlowLog",
                                "smartag:ModifyFlowLogAttribute"
                            ],
                            "Resource": "*",
                            "Effect": "Allow"
                        }
                    ]
                }
                ```

        For more information about the parameters, see [Create a custom policy](/intl.en-US/Policy Management/Custom policies/Create a custom policy.md).

    5.  In the left-side navigation pane, choose **Identities** \> **Users**.

    6.  On the **Users** page, find the RAM user and click **Add Permissions** in the **Actions** column.

    7.  In the **Add Permissions** panel, confirm **Authorized Scope** and **Principal**.

    8.  In the **Select Policy** section, click **Custom Policy**, select the permission that you created, and then click **OK**.

        After you complete the preceding steps, you can perform [Step 1](#step_hok_50y_5zo) to view the permission policy that is attached to the RAM user.


