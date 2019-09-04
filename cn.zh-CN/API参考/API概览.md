# API概览 {#doc_15412 .concept}

智能接入网关提供以下相关API接口。

## 智能接入网关 {#section_tpq_kia_juc .section}

|API|描述|
|---|--|
|[DowngradeSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/DowngradeSmartAccessGateway.md)|使用DowngradeSmartAccessGateway接口降低智能接入网关实例的带宽。|
|[BindSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/BindSmartAccessGateway.md)|调用BindSmartAccessGateway接口将智能接入网关绑定到指定的云连接网中。|
|[UnbindSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/UnbindSmartAccessGateway.md)|调用UnbindSmartAccessGateway将智能接入网关从指定的云连接网中解绑。|
|[UpgradeSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/UpgradeSmartAccessGateway.md)|调用UpgradeSmartAccessGateway接口升高智能接入网关实例的带宽。|
|[DescribeSmartAccessGatewayVersions](cn.zh-CN/API参考/智能接入网关/DescribeSmartAccessGatewayVersions.md)|调用DescribeSmartAccessGatewayVersions查询智能接入网关的软件版本。|
|[GetSmartAccessGatewayUseLimit](cn.zh-CN/API参考/智能接入网关/GetSmartAccessGatewayUseLimit.md)|调用GetSmartAccessGatewayUseLimit查询可购买的智能接入网关数量。|
|[DescribeRegions](cn.zh-CN/API参考/智能接入网关/DescribeRegions.md)|调用DescribeRegions查询可用地域。|
|[CreateSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/CreateSmartAccessGateway.md)|调用CreateSmartAccessGateway智能接入网关实例。|
|[DescribeSmartAccessGateways](cn.zh-CN/API参考/智能接入网关/DescribeSmartAccessGateways.md)|调用DescribeSmartAccessGateways查询已创建的智能接入网关。|
|[UpdateSmartAccessGatewayVersion](cn.zh-CN/API参考/智能接入网关/UpdateSmartAccessGatewayVersion.md)|调用UpdateSmartAccessGatewayVersion升级智能接入网关的软件版本。|
|[ModifySmartAccessGateway](cn.zh-CN/API参考/智能接入网关/ModifySmartAccessGateway.md)|调用ModifySmartAccessGateway修改智能接入网关的配置。|
|[ActivateSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/ActivateSmartAccessGateway.md)|调用ActivateSmartAccessGateway激活智能接入网关设备。|
|[DescribeSmartAccessGatewayHa](cn.zh-CN/API参考/智能接入网关/DescribeSmartAccessGatewayHa.md)|查询智能接入网关的高可用配置。|
|[AddSnatEntry](cn.zh-CN/API参考/智能接入网关/AddSnatEntry.md)|调用AddSnatEntry给智能接入网关实例添加私网SNAT条目。|
|[DescribeSnatEntries](cn.zh-CN/API参考/智能接入网关/DescribeSnatEntries.md)|调用DescribeSnatEntries查询智能接入网关实例绑定的SNAT条目。|
|[DeleteSnatEntry](cn.zh-CN/API参考/智能接入网关/DeleteSnatEntry.md)|调用DeleteSnatEntry删除指定智能接入网关绑定的SNAT条目。|
|[AddDnatEntry](cn.zh-CN/API参考/智能接入网关/AddDnatEntry.md)|调用AddDnatEntry给智能接入网关实例添加DNAT条目。|
|[DescribeDnatEntries](cn.zh-CN/API参考/智能接入网关/DescribeDnatEntries.md)|调用DescribeDnatEntries查询智能接入网关实例绑定的DNAT条目。|
|[DeleteDnatEntry](cn.zh-CN/API参考/智能接入网关/DeleteDnatEntry.md)|调用DeleteDnatEntry删除指定智能接入网关实例绑定的DNAT条目。|
|[RebootSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/RebootSmartAccessGateway.md)|调用RebootSmartAccessGateway重启智能接入网关实例。|
|[UnlockSmartAccessGateway](cn.zh-CN/API参考/智能接入网关/UnlockSmartAccessGateway.md)|调用UnlockSmartAccessGateway解锁智能接入网关实例。|

## 云连接网 {#section_ezl_y3q_3js .section}

|API|描述|
|---|--|
|[DeleteCloudConnectNetwork](cn.zh-CN/API参考/云连接网/DeleteCloudConnectNetwork.md)|调用DeleteCloudConnectNetwork删除云连接网。|
|[GetCloudConnectNetworkUseLimit](cn.zh-CN/API参考/云连接网/GetCloudConnectNetworkUseLimit.md)|调用GetCloudConnectNetworkUseLimit查询当前账号在指定区域内的云连接网个数限制。|
|[CreateCloudConnectNetwork](cn.zh-CN/API参考/云连接网/CreateCloudConnectNetwork.md)|调用CreateCloudConnectNetwork创建云连接网。|
|[ModifyCloudConnectNetwork](cn.zh-CN/API参考/云连接网/ModifyCloudConnectNetwork.md)|调用ModifyCloudConnectNetwork修改云连接网的名称和描述。|
|[DescribeCloudConnectNetworks](cn.zh-CN/API参考/云连接网/DescribeCloudConnectNetworks.md)|调用DescribeCloudConnectNetworks查询已创建的云连接网。|
|[GrantInstanceToCbn](cn.zh-CN/API参考/云连接网/GrantInstanceToCbn.md)|调用GrantInstanceToCbn将云企业网实例授权给云连接网。|
|[RevokeInstanceFromCbn](cn.zh-CN/API参考/云连接网/RevokeInstanceFromCbn.md)|调用RevokeInstanceFromCbn撤销云企业网对云连接网的授权。|
|[DescribeGrantRules](cn.zh-CN/API参考/云连接网/DescribeGrantRules.md)|调用DescribeGrantRules查询绑定的云连接网的授权规则。|

## 访问控制 {#section_fb8_mnv_mol .section}

|API|描述|
|---|--|
|[DescribeACLs](cn.zh-CN/API参考/访问控制/DescribeACLs.md)|调用DescribeACLs查询访问控制信息。|
|[ModifyACL](cn.zh-CN/API参考/访问控制/ModifyACL.md)|调用ModifyACL修改访问控制。|
|[DeleteACL](cn.zh-CN/API参考/访问控制/DeleteACL.md)|调用DeleteACL删除访问控制。|
|[AssociateACL](cn.zh-CN/API参考/访问控制/AssociateACL.md)|调用AssociateACL将访问控制与智能接入网关实例绑定。|
|[DisassociateACL](cn.zh-CN/API参考/访问控制/DisassociateACL.md)|调用DisassociateACL将智能接入网关实例跟访问控制解绑。|
|[AddACLRule](cn.zh-CN/API参考/访问控制/AddACLRule.md)|调用AddACLRule添加访问控制规则。|
|[DeleteACLRule](cn.zh-CN/API参考/访问控制/DeleteACLRule.md)|调用DeleteACLRule删除访问控制规则。|
|[ModifyACLRule](cn.zh-CN/API参考/访问控制/ModifyACLRule.md)|调用ModifyACLRule修改访问控制规则。|
|[CreateACL](cn.zh-CN/API参考/访问控制/CreateACL.md)|调用CreateACL创建访问控制。|
|[DescribeACLAttribute](cn.zh-CN/API参考/访问控制/DescribeACLAttribute.md)|调用DescribeACLAttribute批量查询访问控制，需要增加Name参数，支持按照Name过滤。|

## 智能接入网关APP {#section_qwe_5po_y8o .section}

|API|描述|
|---|--|
|[CreateSmartAccessGatewaySoftware](cn.zh-CN/API参考/智能接入网关APP/CreateSmartAccessGatewaySoftware.md)|调用CreateSmartAccessGatewaySoftware创建智能接入网关APP。|
|[CreateSmartAccessGatewayClientUser](cn.zh-CN/API参考/智能接入网关APP/CreateSmartAccessGatewayClientUser  .md)|调用CreateSmartAccessGatewayClientUser创建用户。|
|[DescribeSmartAccessGatewayClientUsers](cn.zh-CN/API参考/智能接入网关APP/DescribeSmartAccessGatewayClientUsers.md)|调用DescribeSmartAccessGatewayClientUsers查询智能接入网关APP实例用户列表。|
|[ResetSmartAccessGatewayClientUserPassword](cn.zh-CN/API参考/智能接入网关APP/ResetSmartAccessGatewayClientUserPassword.md)|调用ResetSmartAccessGatewayClientUserPassword重置APP客户端密码。|
|[DeleteSmartAccessGatewayClientUser](cn.zh-CN/API参考/智能接入网关APP/DeleteSmartAccessGatewayClientUser.md)|调用DeleteSmartAccessGatewayClientUser删除APP客户端用户。|
|[ModifySmartAccessGatewayClientUser](cn.zh-CN/API参考/智能接入网关APP/ModifySmartAccessGatewayClientUser.md)|调用ModifySmartAccessGatewayClientUser修改用户带宽。|
|[DescribeUserOnlineClientStatistics](cn.zh-CN/API参考/智能接入网关APP/DescribeUserOnlineClientStatistics.md)|调用DescribeUserOnlineClientStatistics查询指定智能接入网关APP实例用户数统计。|
|[KickOutClients](cn.zh-CN/API参考/智能接入网关APP/KickOutClients.md)|调用KickOutClients根据智能接入网关APP实例ID和用户名，剔除在线连接。|
|[DescribeUserOnlineClients](cn.zh-CN/API参考/智能接入网关APP/DescribeUserOnlineClients.md)|调用DescribeUserOnlineClients根据用户名和智能接入网关APP实例ID查询指定用户在线连接列表。|
|[DescribeSagOnlineClientStatistics](cn.zh-CN/API参考/智能接入网关APP/DescribeSagOnlineClientStatistics.md)|调用DescribeSagOnlineClientStatistics查询当前用户智能接入网关APP实例在线连接数据。|
|[DescribeUserFlowStatistics](cn.zh-CN/API参考/智能接入网关APP/DescribeUserFlowStatistics.md)|调用DescribeUserOnlineClients查询指定智能接入网关APP实例下用户的流量统计。|

## 流日志 {#section_olz_fqz_qls .section}

|API|描述|
|---|--|
|[CreateFlowLog](cn.zh-CN/API参考/流日志/CreateFlowLog.md)|调用CreateFlowlog创建一个流日志。|
|[ModifyFlowLogAttribute](cn.zh-CN/API参考/流日志/ModifyFlowLogAttribute.md)|调用ModifyFlowLogAttribute编辑流日志实例。|
|[DescribeFlowLogs](cn.zh-CN/API参考/流日志/DescribeFlowLogs.md)|调用DescribeFlowLogs查询流日志。|
|[DeleteFlowLog](cn.zh-CN/API参考/流日志/DeleteFlowLog.md)|调用DeleteFlowLog删除一个流日志实例。|
|[ActiveFlowLog](cn.zh-CN/API参考/流日志/ActiveFlowLog.md)|调用ActiveFlowLog启动流日志。|
|[DeactiveFlowLog](cn.zh-CN/API参考/流日志/DeactiveFlowLog.md)|调用DeactiveFlowLog停止流日志。|
|[AssociateFlowLog](cn.zh-CN/API参考/流日志/AssociateFlowLog.md)|调用AssociateFlowLog绑定智能接入网关实例。|
|[DisassociateFlowLog](cn.zh-CN/API参考/流日志/DisassociateFlowLog.md)|调用DisassociateFlowLog解绑智能接入网关实例。|
|[DescribeFlowLogSags](cn.zh-CN/API参考/流日志/DescribeFlowLogSags.md)|调用DescribeFlowLogSags查询流日志绑定的智能接入网关实例。|
|[DescribeUnbindFlowLogSags](cn.zh-CN/API参考/流日志/DescribeUnbindFlowLogSags.md)|调用DescribeUnbindFlowLogSags查询未绑定流日志的智能接入网关实例。|

