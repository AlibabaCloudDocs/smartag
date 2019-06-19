# API概览 {#doc_15412 .concept}

智能接入网关提供以下相关API接口。

## 访问控制 {#section_76v_oua_xge .section}

|API|描述|
|---|--|
|[DescribeACLs](~~112858~~)|调用DescribeACLs查询访问控制信息。|
|[ModifyACL](~~112860~~)|调用ModifyACL修改访问控制。|
|[DeleteACL](~~112862~~)|调用DeleteACL删除访问控制。|
|[AssociateACL](~~112863~~)|调用AssociateACL将访问控制与智能接入网关实例绑定。|
|[DisassociateACL](~~112865~~)|调用DisassociateACL将智能接入网关实例跟访问控制解绑。|
|[AddACLRule](~~112893~~)|调用AddACLRule添加访问控制规则。|
|[DeleteACLRule](~~112894~~)|调用DeleteACLRule删除访问控制规则。|
|[ModifyACLRule](~~112896~~)|调用ModifyACLRule修改访问控制规则。|
|[CreateACL](~~112536~~)|调用CreateACL创建访问控制。|
|[DescribeACLAttribute](~~112856~~)|调用DescribeACLAttribute批量查询访问控制，需要增加Name参数，支持按照Name过滤。|

## 智能接入网关软件版 {#section_krc_q5e_tke .section}

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

