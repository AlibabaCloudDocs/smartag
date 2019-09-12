# RevokeSagInstanceFromCcn {#doc_api_Smartag_RevokeSagInstanceFromCcn .reference}

调用RevokeSagInstanceFromCcn从云连接网撤销智能接入网关实例的加入授权。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=RevokeSagInstanceFromCcn&type=RPC&version=2018-03-13)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CcnInstanceId|String|是|ccn-jf\*\*\*\*\*\*\*\*|云连接网实例ID。

 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所在的地域ID。

 |
|SmartAGId|String|是|sag-hd\*\*\*\*\*\*\*\*\*\*\*\*\*\*|智能接入网关实例ID。

 |
|Action|String|否|RevokeSagInstanceFromCcn|要执行的操作。

 取值：**RevokeSagInstanceFromCcn**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BCB97739-0CB5-4C94-9A5C-13051FFAB0E9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=RevokeSagInstanceFromCcn
&CcnInstanceId=ccn-jf********
&RegionId=cn-hangzhou
&SmartAGId=sag-hd**************
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RevokeSagInstanceFromCcnResponse>
	  <RequestId>BCB97739-0CB5-4C94-9A5C-13051FFAB0E9</RequestId>
    </RevokeSagInstanceFromCcnResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"BCB97739-0CB5-4C94-9A5C-13051FFAB0E9"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|智能网关实例ID为空。|
|400|CCN.InvalidId|You must specify the CCN instance ID.|云连接网实例ID不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

