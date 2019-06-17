# CreateCloudConnectNetwork {#doc_api_Smartag_CreateCloudConnectNetwork .reference}

调用CreateCloudConnectNetwork创建云连接网。

云连接网是由阿里云分布式接入网关组成的设备接入矩阵。您可以将云连接网绑定到云企业网，实现线下接入矩阵和云上中心矩阵全连接。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=CreateCloudConnectNetwork)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|IsDefault|Boolean|是|false|是否默认创建。

 如果客户没有ccn在绑定时，会给用户默认创建一个ccn。

 |
|Action|String|否|CreateCloudConnectNetwork|要执行的操作。

 取值： **CreateCloudConnectNetwork**

 |
|CidrBlock|String|否|172.16.22.0/24|私网网段。

 |
|Description|String|否|ccn描述|云连接网的描述。

 长度为2-256个字符，必须以字母或中文开头，但不能以`http://`或 `https://`开头。

 |
|Name|String|否|ccn名称|云连接网的名称。

 长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或 `https://`开头。

 |
|RegionId|String|否|cn-hangzhou|云连接网的所属区域。取值： cn-shanghai：中国大陆

 |
|SnatCidrBlock|String|否|172.16.22.3/24|SNAT内网网段。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CcnId|String|ccn-l9340rlu5ens\*\*\*\*\*|云连接网ID。

 |
|CidrBlock|String|172.16.22.0/24|私网网段。

 |
|Description|String|ccn描述|云连接网说明。

 |
|Name|String|ccn名称|云连接网名称。

 |
|RequestId|String|F0C4D78D-C60E-4A3B-A652-3A2835305C0B|请求ID。

 |
|SnatCidrBlock|String|172.16.22.3/24|SNAT内网网段。

 |
|Status|String|Active|云连接网实例状态。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://smartag.cn-shanghai.aliyuncs.com/?Action=CreateCloudConnectNetwork
&Name=DocTest
&CommonParameters

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCloudConnectNetworkResponse>
  <Name>DocTest</Name>
  <Status>Active</Status>
  <RequestId>F0C4D78D-C60E-4A3B-A652-3A2835305C0B</RequestId>
  <CcnId>ccn-l9340rlu5enstmzj5i</CcnId>
</CreateCloudConnectNetworkResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Name":"DocTest",
	"Status":"Active",
	"RequestId":"F0C4D78D-C60E-4A3B-A652-3A2835305C0B",
	"CcnId":"ccn-l9340rlu5enstmzj5i"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|InvalidDescription|Description not valid.|详情描述超过长度限制|
|403|InvalidName|Name not valid.|名称不合法|
|403|CcnAmountLimit|The CCNs you created has reached the limit, you can raise the limit by application.|您创建的智能连接网数量已经达到限额，您可以通过工单申请提升限额|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Smartag)

