# DescribeSmartAccessGateways {#doc_api_Smartag_DescribeSmartAccessGateways .reference}

调用DescribeSmartAccessGateways查询已创建的智能接入网关。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGateways)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AclIds|String|否|acl-xhwhyuo43l0n\*\*\*\*\*\*|智能接入网关实例绑定的访问控制规则。

 |
|Action|String|否|DescribeSmartAccessGateways|执行的操作。

 取值： **DescribeSmartAccessGateways**

 |
|AssociatedCcnId|String|否|ccn-bxuau4ezctt\*\*\*\*\*\*|绑定的云连接网ID。

 |
|InstanceType|String|否|sag-100wm|实例类型。

 |
|Name|String|否|sag|智能接入网关名称。

 |
|PageNumber|String|否|2|实例状态列表的页码，默认值是1。

 |
|PageSize|String|否|1|分页查询时设置的每页行数，默认值为10，最大值为50。

 |
|RegionId|String|否|cn-hangzhou|智能接入网关的所属区域。

 |
|SerialNumber|String|否|sag32a30121|智能接入网关的序列号。

 |
|SmartAGId|String|否|sag-c3m3n1khz58l\*\*\*\*\*\*|智能接入网关ID。

 |
|Status|String|否|Ordered|智能接入网关状态，取值：

 -   Ordered：已下单
-   Delivered：已发货
-   Received：已收货
-   Returning：退货中
-   ACTIVE：活跃
-   Init：初始化

 |
|UnboundAclIds|String|否|acl-sjfbgngj\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*|未关联到该ACL，多个ID用逗号隔开。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|2|当前页码。

 |
|PageSize|Integer|2|当前分页包含多少条目。

 |
|RequestId|String|7F26258D-8BDE-4EC4-BB4D-4DDC64F64F77|请求ID。

 |
|SmartAccessGateways| | |智能接入网关的详细信息。

 |
|└AclIds|String|acl-shfhfhhfbnvkdg\*\*\*\*\*\*|智能接入网关实例绑定的访问控制规则。

 |
|└AssociatedCcnId|String|ccn-bxuau4ezctts\*\*\*\*\*\*|绑定的云连接网ID。

 |
|└AssociatedCcnName|String|ccn|绑定的云连接网名称。

 |
|└CidrBlock|String|192.168.0.1/24|线下机构客户端通信的私网网段。

 |
|└City|String|杭州|城市。

 |
|└CreateTime|Long|1523604565000|智能接入网关的创建时间。

 |
|└DataPlan|Long|5|套餐流量。

 |
|└Description|String|sag描述|智能接入网关描述。

 |
|└EndTime|Long|1526227200000|智能接入网关的到期时间。

 |
|└HardwareVersion|String|sag-100wm|实例类型。如 sag-1000和sag-100wm。

 |
|└MaxBandwidth|String|3|智能接入网关的带宽。

 |
|└Name|String|sag|智能接入网关名称。

 |
|└SecurityLockThreshold|Integer|3600|离线锁定功能用户设定的阈值，大于等于0。

 单位：秒。

 |
|└SerialNumber|String|sag32a9034958a|智能接入网关的序列号。

 |
|└SmartAGId|String|sag-v0fkpk4akfz5\*\*\*\*\*\*|智能接入网关ID。

 |
|└SnatEntries| | |SNAT配置条目。

 |
|└CidrBlock|String|10.10.10.1|私网网段。

 |
|└SnatIp|String|10.10.10.5|外网地址是云连接网SNAT网段内的一个IP地址，不填则系统自动分配。

 |
|└SoftwareVersion|String|1.0.0|智能接入网关的软件版本。

 |
|└Status|String|Init|智能接入网关的状态。

 |
|└UserCount|Integer|12|用户账号个数。

 |
|TotalCount|Integer|2|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSmartAccessGateways
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSmartAccessGatewaysResponse>
  <PageNumber>1</PageNumber>
  <SmartAccessGateways>
    <SmartAccessGateway>
      <Name>测试</Name>
      <SmartAGId>sag-v0fkpk4akfz5hebved</SmartAGId>
      <Status>Init</Status>
      <AssociatedCcnName>xuehao</AssociatedCcnName>
      <AssociatedCcnId>ccn-bxuau4ezctts2kfxyr</AssociatedCcnId>
      <CreateTime>1523604565000</CreateTime>
      <EndTime>1526227200000</EndTime>
      <SoftwareVersion>1.0.0</SoftwareVersion>
      <MaxBandwidth>1M</MaxBandwidth>
    </SmartAccessGateway>
    <SmartAccessGateway>
      <Name>xuehao</Name>
      <SmartAGId>sag-c3m3n1khz58lbfhfw1</SmartAGId>
      <CidrBlock>0.0.0.0/0</CidrBlock>
      <Status>Init</Status>
      <AssociatedCcnName>测试</AssociatedCcnName>
      <AssociatedCcnId>ccn-kygbldwikzdg2g9b8e</AssociatedCcnId>
      <CreateTime>1523597460000</CreateTime>
      <EndTime>1526227200000</EndTime>
      <SoftwareVersion>1.0.0</SoftwareVersion>
      <MaxBandwidth>3M</MaxBandwidth>
    </SmartAccessGateway>
  </SmartAccessGateways>
  <TotalCount>2</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>7F26258D-8BDE-4EC4-BB4D-4DDC64F64F77</RequestId>
</DescribeSmartAccessGatewaysResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"SmartAccessGateways":{
		"SmartAccessGateway":[
			{
				"SmartAGId":"sag-v0fkpk4akfz5hebved",
				"Name":"测试",
				"SoftwareVersion":"1.0.0",
				"Status":"Init",
				"AssociatedCcnName":"xuehao",
				"AssociatedCcnId":"ccn-bxuau4ezctts2kfxyr",
				"CreateTime":1523604565000,
				"EndTime":1526227200000,
				"MaxBandwidth":"1M"
			},
			{
				"SmartAGId":"sag-c3m3n1khz58lbfhfw1",
				"Name":"xuehao",
				"SoftwareVersion":"1.0.0",
				"Status":"Init",
				"CidrBlock":"0.0.0.0/0",
				"AssociatedCcnName":"测试",
				"AssociatedCcnId":"ccn-kygbldwikzdg2g9b8e",
				"CreateTime":1523597460000,
				"EndTime":1526227200000,
				"MaxBandwidth":"3M"
			}
		]
	},
	"PageSize":10,
	"RequestId":"7F26258D-8BDE-4EC4-BB4D-4DDC64F64F77"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

