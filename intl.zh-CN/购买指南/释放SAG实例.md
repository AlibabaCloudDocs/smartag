---
keyword: [释放SAG实例, 删除SAG实例]
---

# 释放SAG实例

您可以释放一个不需要的智能接入网关SAG（Smart Access Gateway）实例。

## SAG实例释放规则

-   SAG硬件版和VCPE版实例
    -   如果在实例到期前需要释放实例，请申请退款流程，退款完成后系统自动释放实例。关于退款的更多信息，请参见[阿里云产品提前退订规则](https://www.alibabacloud.com/help/zh/doc-detail/102721.htm?spm=a2c63.p38356.b99.6.7ebe6f57zoOllI)。
    -   如果在实例到期后需要释放实例，请在实例到期7天后在控制台自行删除实例。具体操作，请参见[删除SAG硬件版或VCPE版实例](#section_hca_u4v_ddm)。
-   SAG APP版实例
    -   如果在实例到期前需要释放实例，请申请退款流程，退款完成后系统自动释放实例。关于退款的更多信息，请参见[阿里云产品提前退订规则](https://www.alibabacloud.com/help/zh/doc-detail/102721.htm?spm=a2c63.p38356.b99.6.7ebe6f57zoOllI)。
    -   SAG APP实例到期7天后会自动释放。更多信息，请参见[SAG APP实例停机、释放和受限状态说明](/intl.zh-CN/APP手册/SAG APP计费说明.md)。

## 删除SAG硬件版或VCPE版实例

删除SAG实例前，请确保实例已满足以下条件：

-   SAG实例未绑定任何云连接网CCN（Cloud Connect Network）或边界路由器VBR（Virtual border router）实例。如已绑定网络实例，请先进行解绑。具体操作，请参见[解绑网络实例](/intl.zh-CN/配置指南/云上网络配置/解绑网络实例.md)。
-   SAG实例已处于欠费锁定状态且超过7天。关于SAG实例状态的更多信息，请参见[设备状态监控](/intl.zh-CN/监控与运维/设备状态监控.md)。

1.  登录[智能接入网关管理控制台](https://smartag.console.aliyun.com)。

2.  在顶部菜单栏，选择目标区域。

3.  在**智能接入网关**页面，找到目标实例，在**操作**列选择**![更多](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8799952261/p101595.png)** \> **删除**。

4.  在**删除智能接入网关实例**对话框，确认目标实例信息，然后单击**确定**。


