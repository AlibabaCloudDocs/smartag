# DescribeSmartAccessGatewayHa {#doc_api_Smartag_DescribeSmartAccessGatewayHa .reference}

查询智能接入网关的高可用配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeSmartAccessGatewayHa)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-shanghai|智能接入网关实例的地域ID。

 |
|SmartAGId|String|是|sag-pno62188piyc6txxxxx|要查询的智能接入网关实例ID。

 |
|Action|String|否|DescribeSmartAccessGatewayHa|要执行的操作，取值：**DescribeSmartAccessGatewayHa**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BackupDeviceId|String|sag11axxxx|备用设备序列号。

 |
|DeviceLevelBackupState|String|OFF|设备级别备份状态。取值：**OFF|ON**。

 |
|DeviceLevelBackupType|String|ColdStandbyMode|设备级别高可用类型：

 -   ColdStandbyMode：双机冷备
-   HotStandbyMode：双机热备
-   NoBackupMode：无备份

 |
|LinkBackupInfoList| | |备用链路信息。

 |
|BackupLinkId|String|wan1|备份连接ID。

 |
|BackupLinkState|String|down|备份连接状态。

 |
|LinkLevelBackupState|String|ON|连接级别备份状态。

 |
|LinkLevelBackupType|String|StandbyMode|连接级别备份类型。

 |
|MainLinkId|String|lte|主连接ID。

 |
|MainLinkState|String|up|主连接状态。

 |
|MainDeviceId|String|sag11axxxx|主设备序列号。

 |
|RequestId|String|582FE511-FEFE-42BC-BBF4-4F8ECF92Exxx|请求ID。

 |
|SmartAGId|String|sag-i8mogwi9kisigc3xxxx|智能接入网关实例ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSmartAccessGatewayHa
&RegionId=cn-hangzhou
&SmartAGId=sag-pno62188piyc6txxxxx
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSmartAccessGatewayHaResponse>
  <SmartAGId>sag-i8mogwi9kisigcxxxx</SmartAGId>
  <DeviceLevelBackupState>OFF</DeviceLevelBackupState>
  <LinkBackupInfoList>
    <LinkBackupInfoList>
      <LinkLevelBackupType>StandbyMode</LinkLevelBackupType>
      <MainLinkId>lte</MainLinkId>
      <BackupLinkState>down</BackupLinkState>
      <LinkLevelBackupState>ON</LinkLevelBackupState>
      <BackupLinkId>wan1</BackupLinkId>
      <MainLinkState>up</MainLinkState>
    </LinkBackupInfoList>
  </LinkBackupInfoList>
  <RequestId>582FE511-FEFE-42BC-BBF4-4F8ECF92E3C6</RequestId>
</DescribeSmartAccessGatewayHaResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SmartAGId":"sag-i8mogwi9kisigcxxxx",
	"DeviceLevelBackupState":"OFF",
	"LinkBackupInfoList":{
		"LinkBackupInfoList":[
			{
				"LinkLevelBackupType":"StandbyMode",
				"MainLinkId":"lte",
				"LinkLevelBackupState":"ON",
				"BackupLinkState":"down",
				"MainLinkState":"up",
				"BackupLinkId":"wan1"
			}
		]
	},
	"RequestId":"582FE511-FEFE-42BC-BBF4-4F8ECF92E3C6"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

