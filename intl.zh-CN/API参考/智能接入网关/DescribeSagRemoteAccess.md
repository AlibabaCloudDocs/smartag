# DescribeSagRemoteAccess

调用DescribeSagRemoteAccess查询智能接入网关设备远程登录信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSagRemoteAccess&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSagRemoteAccess|要执行的操作。

 取值：**DescribeSagRemoteAccess**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SerialNumber|String|是|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|SmartAGId|String|是|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|错误码。200标识查询任务成功。 |
|Message|String|successful|错误信息。Successful标识查询任务成功。 |
|RemoteAccesses|Array of RemoteAccess| |智能接入网关设备远程登录信息。 |
|RemoteAccess| | | |
|RemoteAccessIp|String|192.XX.XX.1|远程登录私网IP地址。 |
|SerialNumber|String|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|RequestId|String|E38E950D-28A4-4C41-9428-A8908EC6AE5C|请求ID。 |
|SmartAGId|String|sag-1um5x5nwhilymw\*\*\*\*|智能接入网关实例ID。 |
|Success|Boolean|true|标识查询任务是否成功。

 -   **true**：表示查询任务成功。
-   **false**：表示查询任务未成功。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSagRemoteAccess
&RegionId=cn-shanghai
&SerialNumber=sage62x022502****
&SmartAGId=sag-1um5x5nwhilymw****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeSagRemoteAccessResponse>
  <SmartAGId>sag-kxe2cv7hot7qrv****</SmartAGId>
  <RemoteAccesses>
        <RemoteAccess>
              <RemoteAccessIp></RemoteAccessIp>
              <SerialNumber>sage62x022502****</SerialNumber>
        </RemoteAccess>
  </RemoteAccesses>
  <Message>successful</Message>
  <RequestId>2E2A56D0-D2BD-4D0B-9314-D355A5C67EBA</RequestId>
  <Success>true</Success>
  <Code>200</Code>
</DescribeSagRemoteAccessResponse>
```

`JSON` 格式

```
{
	"SmartAGId": "sag-kxe2cv7hot7qrv****",
	"RemoteAccesses": {
		"RemoteAccess": [
			{
				"RemoteAccessIp": "",
				"SerialNumber": "sage62x022502****"
			}
		]
	},
	"Message": "successful",
	"RequestId": "2E2A56D0-D2BD-4D0B-9314-D355A5C67EBA",
	"Success": true,
	"Code": "200"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InstanceNotExit|The specified instance does not exist.|指定的实例不存在|
|400|InvalidId.SN|The specified smart access gateway serial number does not exist.|输入的SAG序列号不存在。|
|500|InternalError|An error occurred while processing your request.|请求失败，发生未知错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

