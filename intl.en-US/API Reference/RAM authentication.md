# RAM authentication {#concept_avx_2vm_l2b .concept}

Before calling Smart Access Gateway APIs using a RAM user, you must grant the RAM user the corresponding permission from the primary account by creating an authentication policy. An Alibaba Cloud Resource Name \(ARN\) is used as a unique description of a resource in the authorization rule. The following table lists the ARNs of Smart Access Gateway APIs.

|Resource type|ARN|
|:------------|:--|
|CreateSmartAccessGateway|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/\*|
|UpdateSmartAccessGatewayVersion|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/$\{smartag-id\}|
|DescribeSmartAccessGateways|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/\*|
|ModifySmartAccessGateway|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/$\{smartag-id\}|
|GetSmartAccessGatewayUseLimit|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/\*|
|GetCloudConnectNetworkUseLimit|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/\*|
|CreateCloudConnectNetwork|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/\*|
|DeleteCloudConnectNetwork|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/$\{ccnid\}|
|ModifyCloudConnectNetwork|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/$\{ccnid\}|
|DescribeCloudConnectNetworks|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/\*|
|BindSmartAccessGateway| acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/$\{ccnid\}

 acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/$\{smartag-id\}

 |
|UnbindSmartAccessGateway| acs:smartag:$\{region-id\}:$\{resource-owner-id\}:ccn/$\{ccnid\}

 acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/$\{smartag-id\}

 |
|ActivateSmartAccessGateway|acs:smartag:$\{region-id\}:$\{resource-owner-id\}:smartag/$\{smartag-id\}|

