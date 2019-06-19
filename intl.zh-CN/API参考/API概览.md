# API概览 {#doc_15412 .concept}

智能接入网关提供以下相关API接口。

## 智能接入网关 {#section_0do_ezk_lsx .section}

|API|描述|
|---|--|
|[BindSmartAccessGateway](~~69805~~)|调用BindSmartAccessGateway接口将智能接入网关绑定到指定的云连接网中。|
|[UnbindSmartAccessGateway](~~69834~~)|调用UnbindSmartAccessGateway将智能接入网关从指定的云连接网中解绑。|
|[UpgradeSmartAccessGateway](~~100566~~)|调用UpgradeSmartAccessGateway接口升高智能接入网关实例的带宽。|
|[DescribeSmartAccessGatewayVersions](~~69825~~)|调用DescribeSmartAccessGatewayVersions查询智能接入网关的软件版本。|
|[GetSmartAccessGatewayUseLimit](~~69828~~)|调用GetSmartAccessGatewayUseLimit查询可购买的智能接入网关数量。|
|[DescribeRegions](~~69813~~)|调用DescribeRegions查询可用地域。|
|[CreateSmartAccessGateway](~~99993~~)|调用CreateSmartAccessGateway智能接入网关实例。|
|[DescribeSmartAccessGateways](~~69815~~)|调用DescribeSmartAccessGateways查询已创建的智能接入网关。|
|[UpdateSmartAccessGatewayVersion](~~69836~~)|调用UpdateSmartAccessGatewayVersion升级智能接入网关的软件版本。|
|[ModifySmartAccessGateway](~~69833~~)|调用ModifySmartAccessGateway修改智能接入网关的配置。|

## 云连接网 {#section_jki_xo8_ot6 .section}

|API|描述|
|---|--|
|[DeleteCloudConnectNetwork](~~69810~~)|调用DeleteCloudConnectNetwork删除云连接网。|
|[GetCloudConnectNetworkUseLimit](~~69826~~)|调用GetCloudConnectNetworkUseLimit查询当前账号在指定区域内的云连接网个数限制。|
|[CreateCloudConnectNetwork](~~69809~~)|调用CreateCloudConnectNetwork创建云连接网。|
|[ModifyCloudConnectNetwork](~~69830~~)|调用ModifyCloudConnectNetwork修改云连接网的名称和描述。|
|[DescribeCloudConnectNetworks](~~69811~~)|调用DescribeCloudConnectNetworks查询已创建的云连接网。|

## 访问控制 {#section_w4z_lde_s5o .section}

|API|描述|
|---|--|
|[DescribeACLs](~~114006~~)|调用DescribeACLs查询访问控制信息。|
|[ModifyACL](~~114007~~)|调用ModifyACL修改访问控制。|
|[DeleteACL](~~114008~~)|调用DeleteACL删除访问控制。|
|[AssociateACL](~~114009~~)|调用AssociateACL将访问控制与智能接入网关实例绑定。|
|[DisassociateACL](~~114013~~)|调用DisassociateACL将智能接入网关实例跟访问控制解绑。|
|[AddACLRule](~~114012~~)|调用AddACLRule添加访问控制规则。|
|[DeleteACLRule](~~114014~~)|调用DeleteACLRule删除访问控制规则。|
|[ModifyACLRule](~~114015~~)|调用ModifyACLRule修改访问控制规则。|
|[CreateACL](~~114016~~)|调用CreateACL创建访问控制。|
|[DescribeACLAttribute](~~114017~~)|调用DescribeACLAttribute批量查询访问控制，需要增加Name参数，支持按照Name过滤。|

## 智能接入网关软件版 {#section_oa8_wb7_bry .section}

|API|描述|
|---|--|
|[CreateSmartAccessGatewaySoftware](~~120540~~)|调用CreateSmartAccessGatewaySoftware创建智能接入网关软件版。|
|[CreateSmartAccessGatewayClientUser](~~120685~~)|调用CreateSmartAccessGatewayClientUser创建用户。|
|[DescribeSmartAccessGatewayClientUsers](~~120687~~)|调用DescribeSmartAccessGatewayClientUsers查询软件版实例用户列表。|
|[ResetSmartAccessGatewayClientUserPassword](~~120704~~)|调用ResetSmartAccessGatewayClientUserPassword重置软件版客户端密码。|
|[DeleteSmartAccessGatewayClientUser](~~120712~~)|调用DeleteSmartAccessGatewayClientUser删除软件客户端用户。|
|[ModifySmartAccessGatewayClientUser](~~120713~~)|调用ModifySmartAccessGatewayClientUser修改用户带宽。|
|[DescribeUserOnlineClientStatistics](~~120719~~)|调用DescribeUserOnlineClientStatistics查询指定智能接入网关软件版实例用户数统计。|
|[KickOutClients](~~120728~~)|调用KickOutClients根据智能接入网关软件版实例ID和用户名，剔除在线连接。|
|[DescribeUserOnlineClients](~~120729~~)|调用DescribeUserOnlineClients根据用户名和智能接入网关软件版实例ID查询指定用户在线连接列表。|
|[DescribeSagOnlineClientStatistics](~~120717~~)|调用DescribeSagOnlineClientStatistics查询当前用户智能接入网关软件版实例在线连接数据。|
|[DescribeUserFlowStatistics](~~120730~~)|调用DescribeUserOnlineClients查询指定智能接入网关软件版实例下用户的流量统计。|

