# 为RAM用户授予QoS策略和流日志功能使用权限

在RAM用户使用智能接入网关的QoS策略和流日志功能前，您需要使用阿里云账号授予目标RAM用户相应功能的使用权限。

1.  查看目标RAM用户已有的授权策略。

    1.  使用阿里云账号登录[RAM控制台](https://ram.console.aliyun.com/)。

    2.  在左侧导航栏，选择**权限管理** \> **授权**。

    3.  在**授权**页面，搜索目标RAM用户，查看其已被授予的权限策略。

        如果该RAM用户已被授予了AliyunSmartAccessGatewayFullAccess权限策略，则该RAM用户可直接使用QoS策略和流日志功能，无需额外的授权操作。您可以单击**AliyunSmartAccessGatewayFullAccess**，查看权限策略详情。AliyunSmartAccessGatewayFullAccess权限策略内容如下。

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

2.  如果您的RAM用户没有被授予AliyunSmartAccessGatewayFullAccess权限。您需要创建自定义权限策略，为目标RAM用户授予相应功能的使用权限。

    如果您的RAM用户要同时使用QoS策略和流日志功能，请按照以下步骤分别为QoS策略和流日志功能创建一个自定义策略并进行授权。

    1.  登录[RAM控制台](https://ram.console.aliyun.com/)。

    2.  在左侧导航栏，选择**权限管理** \> **权限策略管理**。

    3.  在**权限策略管理**页面，单击**创建权限策略**。

    4.  在**新建自定义权限策略**页面，配置以下信息，然后单击**确定**。

        -   **策略名称**：输入策略名称。
        -   **配置模式**：选择策略配置模式。请选择**脚本配置**。
        -   **策略内容**：输入策略内容。
            -   QoS策略

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

            -   流日志

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

        更多参数说明，请参见[创建自定义策略](/intl.zh-CN/权限策略管理/自定义策略/创建自定义策略.md)。

    5.  在左侧导航栏，选择**人员管理** \> **用户**。

    6.  在**用户**页面，搜索目标RAM用户，在其**操作**列单击**添加权限**。

    7.  在**添加权限**面板，确认**授权应用范围**和**被授权主体**。

    8.  在**选择权限**区域，单击**自定义策略**，选择已创建好的自定义策略，然后单击**确定**。

        授权完成后，您可以再通过[步骤1](#step_hok_50y_5zo)查看并确认目标RAM用户已被授予的权限策略。


