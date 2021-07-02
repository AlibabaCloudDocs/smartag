# CreateQos

调用CreateQos接口创建QoS策略实例。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=CreateQos&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|CreateQos|系统规定参数。取值：**CreateQos**。 |
|RegionId|String|是|cn-shanghai|QoS策略实例所在的地域ID。 |
|QosName|String|是|doctest|QoS策略实例名称。

 名称长度为2~100个字符，以大小写字母或中文开头，可包含数字、半角句号（.）、下划线（\_）和短划线（-）。 |
|QosDescription|String|否|testdesc|QoS策略实例描述。

 描述长度为1~512个字符，以大小写字母或中文开头，可包含数字、下划线（\_）和短划线（-）。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AACF5140-783D-48F0-9E4F-E59D716F7D08|请求ID。 |
|QosId|String|rg-acfm2iu4fnc\*\*\*\*|QoS策略实例ID。 |
|ResourceGroupId|String|qos-oek3r2cmvk7m8q\*\*\*\*|QoS策略实例所属资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=CreateQos
&RegionId=cn-shanghai
&QosName=doctest
&QosDescription=testdesc
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<CreateQosResponse>
    <RequestId>AACF5140-783D-48F0-9E4F-E59D716F7D08</RequestId>
    <QosId>rg-acfm2iu4fnc****</QosId>
    <ResourceGroupId>qos-oek3r2cmvk7m8q****</ResourceGroupId>
</CreateQosResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "RequestId" : "AACF5140-783D-48F0-9E4F-E59D716F7D08",
  "QosId" : "rg-acfm2iu4fnc****",
  "ResourceGroupId" : "qos-oek3r2cmvk7m8q****"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|QosAmountLimit|No more QoS can be created. You can submit a ticket to increase the quota of QoSes.|您名下Qos数量已达上线，请提交工单申请提升配额。|
|400|MissParameter.RegionId|You must specify RegionId.|您的输入中缺少必填参数RegionId。|
|400|MissParameter.Name|You must specify Name.|您的输入中缺少必填参数Name。|
|400|InvalidParameter.Name|The specified Name is invalid.|您输入的参数Name不合法。|
|400|InvalidParameter.Description|The specified Description is invalid.|您输入的参数Description不合法。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

