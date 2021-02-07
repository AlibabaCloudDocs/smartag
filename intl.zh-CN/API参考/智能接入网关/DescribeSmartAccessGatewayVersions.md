# DescribeSmartAccessGatewayVersions

调用DescribeSmartAccessGatewayVersions查询智能接入网关设备的软件版本信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayVersions&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeSmartAccessGatewayVersions|要执行的操作。

 取值： **DescribeSmartAccessGatewayVersions**。 |
|RegionId|String|是|cn-hangzhou|智能接入网关实例所属的地域ID。 |
|SmartAGId|String|是|sag-d3m51apgw4po5\*\*\*\*\*|智能接入网关实例ID。 |
|SmartAGSn|String|否|sage62x022502\*\*\*\*|智能接入网关设备序列号。 |
|VersionType|String|否|Device|智能接入网关设备软件类型。取值：

 -   **Device**：（默认值）表示智能接入网关设备运行的操作系统软件。
-   **Dpi**：表示智能接入网关设备运行的应用特征库软件。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|765AB188-69BF-47C6-BEDD-B9FC72BFBB0|请求ID。 |
|SmartAGVersions|Array of SmartAGVersion| |智能接入网关设备软件版本信息列表。 |
|SmartAGVersion| | | |
|CreateTime|Long|1522744623000|软件版本发布时间戳。 |
|Type|String|release|软件版本类型。取值：

 -   **beta**：测试版本。
-   **release**：发布版本。 |
|VersionCode|String|1.0|软件版本号。 |
|VersionName|String|testpackage1|软件版本名称。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeSmartAccessGatewayVersions
&RegionId=cn-hangzhou
&SmartAGId=sag-d3m51apgw4po5*****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeSmartAccessGatewayVersionsResponse>
    <SmartAGVersions>
          <SmartAGVersion>
                <Type>release</Type>
                <CreateTime>1522744623000</CreateTime>
                <VersionCode>1.0</VersionCode>
                <VersionName>testpackage1</VersionName>
          </SmartAGVersion>
    </SmartAGVersions>
    <RequestId>765AB188-69BF-47C6-BEDD-B9FC72BFBB00</RequestId>
</DescribeSmartAccessGatewayVersionsResponse>
```

`JSON`格式

```
{
"SmartAGVersions": {
"SmartAGVersion": [
{
"Type": "release",
"CreateTime": 1522744623000,
"VersionCode": "1.0",
"VersionName": "testpackage1"
}
]
},
"RequestId": "765AB188-69BF-47C6-BEDD-B9FC72BFBB00"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|400|VersionNotExist|The specified version does not exist.|当前指定的版本不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

