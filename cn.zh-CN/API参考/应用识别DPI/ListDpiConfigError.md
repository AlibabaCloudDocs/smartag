# ListDpiConfigError

调用ListDpiConfigError查询应用识别DPI（Deep Packet Inspection）配置异常的信息。

## 背景信息

如果您配置了基于应用的访问控制实例或QoS策略实例，并将其关联到了智能接入网关实例上，您可以通过调用本接口查看您创建的访问控制规则或QoS策略五元组规则是否都已经成功应用到了目标智能接入网关实例上。如果有未应用成功的配置，本接口会将配置异常信息返回给您。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=ListDpiConfigError&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ListDpiConfigError|要执行的操作。

 取值：**ListDpiConfigError**。 |
|DpiConfigType|String|是|qos|配置了DPI功能的实例类型：

 -   **acl**：表示访问控制实例。
-   **qos**：表示QoS策略实例。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SmartAGId|String|是|sag-1e8sgws6b133b8\*\*\*\*|智能接入网关实例ID。 |
|RuleInstanceId|String|否|qos-1strcafl4wghpb\*\*\*\*|配置了DPI功能的实例ID。 |
|NextToken|String|否|caeba0bbb2be03f84eb48b699f0a\*\*\*\*|开始查询下一页的Token。 |
|MaxResults|Integer|否|10|分页查询时允许每页展示的配置异常的最大条目数。

 取值范围：**1**~**100**。

 默认值：**10**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DpiConfigError|Array of DpiConfigError| |DPI配置异常的信息列表。 |
|ErrorType|String|DeviceNotSupported|配置异常类型。

 -   **DeviceNotSupported**：智能接入网关设备不支持DPI功能。
-   **VersionNotSupported**：智能接入网关设备运行的DPI版本过低。
-   **NotEnable**：智能接入网关设备的DPI功能未开启。 |
|RuleConfigErrorList|Array of RuleConfigErrorList| |DPI配置异常的信息列表。 |
|DpiGroupIds|List|1|配置异常的应用组ID列表。

 您可以通过[ListDpiGroups](~~ListDpiGroups~~)查询应用组ID及其包含的应用信息。 |
|DpiSignatureIds|List|1|配置异常的应用ID列表。

 您可以通过[ListDpiSignatures](~~196630~~)查询应用ID及其对应的应用信息。 |
|RuleId|String|qospy-axud4s62gz632b\*\*\*\*|配置异常的应用关联的规则ID列表。

 -   如果您当前查询的是访问控制DPI配置异常信息，则此处显示配置异常的访问控制规则实例ID。
-   如果您当前查询的是QoS策略DPI配置异常信息，则此处显示配置异常的五元组规则实例ID。 |
|SN|String|sag-2160808\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|sag-1e8sgws6b133b8\*\*\*\*|智能接入网关实例ID。 |
|MaxResults|Integer|10|分页查询时允许每页展示的配置异常的最大条目数。 |
|NextToken|String|caeba0bbb2be03f84eb48b699f0a\*\*\*\*|开始查询下一页的Token。 |
|RequestId|String|F47B5293-27B6-48EF-A9C6-E90A41449813|请求ID。 |
|Total|Integer|1|DPI配置异常的总条目数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListDpiConfigError
&DpiConfigType=qos
&RegionId=cn-shanghai
&SmartAGId=sag-1e8sgws6b133b8****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ListDpiConfigErrorResponse>
  <RequestId>27A5B768-4366-4EF3-9524-7FD51331B1DC</RequestId>
  <Total>1</Total>
  <MaxResults>10</MaxResults>
  <DpiConfigError>
        <ErrorType>DeviceNotSupported</ErrorType>
        <RuleConfigErrorList>
              <RuleId>qospy-axud4s62gz632b****</RuleId>
              <DpiGroupIds>1</DpiGroupIds>
        </RuleConfigErrorList>
        <SN>sage62x0526****</SN>
        <SmartAGId>sag-4d6i45zess8nj4****</SmartAGId>
  </DpiConfigError>
</ListDpiConfigErrorResponse>
```

`JSON` 格式

```
{
	"RequestId": "27A5B768-4366-4EF3-9524-7FD51331B1DC",
	"Total": 1,
	"MaxResults": 10,
	"DpiConfigError": [
		{
			"ErrorType": "DeviceNotSupported",
			"RuleConfigErrorList": [
				{
					"DpiSignatureIds": [],
					"RuleId": "qospy-axud4s62gz632b****",
					"DpiGroupIds": [
						"1"
					]
				}
			],
			"SN": "sage62x0526****",
			"SmartAGId": "sag-4d6i45zess8nj4****"
		}
	]
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

