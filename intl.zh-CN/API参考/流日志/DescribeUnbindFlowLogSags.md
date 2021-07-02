# DescribeUnbindFlowLogSags

调用DescribeUnbindFlowLogSags查询指定地域下未绑定流日志实例的智能接入网关实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeUnbindFlowLogSags&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeUnbindFlowLogSags|要执行的操作。取值：**DescribeUnbindFlowLogSags**。 |
|RegionId|String|是|cn-shanghai|要查询的地域ID。

您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C850C10E-9856-45FF-8640-80288BA467DF|请求ID。 |
|Count|Integer|20|总条目数。 |
|Sags|Array of Sag| |智能接入网关实例信息列表。 |
|Sag| | | |
|Description|String|desctest|智能接入网关实例的描述信息。 |
|SmartAGId|String|sag-tzirqx07bvcngm\*\*\*\*|智能接入网关实例ID。 |
|Name|String|sj1000-yf-01|智能接入网关实例名称。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeUnbindFlowLogSags
&RegionId=cn-shanghai
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeUnbindFlowLogSagsResponse>
    <Sags>
        <Sag>
            <Name>jialiang_1000_test_2</Name>
            <SmartAGId>sag-0v3pmd7qpnvx5f****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0625-023417</Name>
            <SmartAGId>sag-0wxbzaf623oz8a****</SmartAGId>
        </Sag>
        <Sag>
            <SmartAGId>sag-13wvoucmn6tjqm****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sj1000-joe-04</Name>
            <SmartAGId>sag-1ihuk7d1qskqk0****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0625-023333</Name>
            <SmartAGId>sag-1tvzazjggo0vac****</SmartAGId>
        </Sag>
        <Sag>
            <Name>joe-casetest-0808</Name>
            <SmartAGId>sag-2c9nradcadqceg****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sj1000-joe_01</Name>
            <SmartAGId>sag-2d102o7focaqxo****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag1000-b5</Name>
            <SmartAGId>sag-60q4iaq068nxt2****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0625-022008</Name>
            <SmartAGId>sag-6m5684w9mhcgzz****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0426-005047</Name>
            <SmartAGId>sag-6t4pxotq7rfz6w****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag-1000-rd-test-env1</Name>
            <SmartAGId>sag-8gocbtkbp9b52c****</SmartAGId>
        </Sag>
        <Sag>
            <Name>tianye-test-vbr</Name>
            <SmartAGId>sag-8z7hn75tubgac2****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sj1000-joe-05</Name>
            <SmartAGId>sag-d866xl31k8lleb****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag1000_box6</Name>
            <SmartAGId>sag-dztg1lco3aacpu****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag1000-ha-for-case</Name>
            <SmartAGId>sag-ewmmi6fcq3gldu****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0613-003734</Name>
            <SmartAGId>sag-fckt58zc4j4b8o****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag-sec-2</Name>
            <SmartAGId>sag-h4j0klyvprxta5****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sn-sag1000-2018-11-08-17-27-11</Name>
            <SmartAGId>sag-h79g3zs0q7nk9f****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sag1000_sh_upgrade</Name>
            <SmartAGId>sag-mrrrlh3xgpyipu****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0625-021924</Name>
            <SmartAGId>sag-ruia2xefxbdm5e****</SmartAGId>
        </Sag>
        <Sag>
            <Name>chengxi_bigbox_cn</Name>
            <SmartAGId>sag-sb7t1efidyc5d5****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sj1000-joe_03</Name>
            <SmartAGId>sag-srgxemiqbyzdxf****</SmartAGId>
        </Sag>
        <Sag>
            <Name>sj1000-yf-01</Name>
            <SmartAGId>sag-tzirqx07bvcngm****</SmartAGId>
        </Sag>
        <Sag>
            <Name>ccn-bvt-china-0-0426-005001</Name>
            <SmartAGId>sag-xboakpuqext95x****</SmartAGId>
        </Sag>
    </Sags>
    <Count>20</Count>
    <RequestId>C850C10E-9856-45FF-8640-80288BA467DF</RequestId>
</DescribeUnbindFlowLogSagsResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "Sags" : {
    "Sag" : [ {
      "Name" : "jialiang_1000_test_2",
      "SmartAGId" : "sag-0v3pmd7qpnvx5f****"
    }, {
      "Name" : "ccn-bvt-china-0-0625-023417",
      "SmartAGId" : "sag-0wxbzaf623oz8a****"
    }, {
      "SmartAGId" : "sag-13wvoucmn6tjqm****"
    }, {
      "Name" : "sj1000-joe-04",
      "SmartAGId" : "sag-1ihuk7d1qskqk0****"
    }, {
      "Name" : "ccn-bvt-china-0-0625-023333",
      "SmartAGId" : "sag-1tvzazjggo0vac****"
    }, {
      "Name" : "joe-casetest-0808",
      "SmartAGId" : "sag-2c9nradcadqceg****"
    }, {
      "Name" : "sj1000-joe_01",
      "SmartAGId" : "sag-2d102o7focaqxo****"
    }, {
      "Name" : "sag1000-b5",
      "SmartAGId" : "sag-60q4iaq068nxt2****"
    }, {
      "Name" : "ccn-bvt-china-0-0625-022008",
      "SmartAGId" : "sag-6m5684w9mhcgzz****"
    }, {
      "Name" : "ccn-bvt-china-0-0426-005047",
      "SmartAGId" : "sag-6t4pxotq7rfz6w****"
    }, {
      "Name" : "sag-1000-rd-test-env1",
      "SmartAGId" : "sag-8gocbtkbp9b52c****"
    }, {
      "Name" : "tianye-test-vbr",
      "SmartAGId" : "sag-8z7hn75tubgac2****"
    }, {
      "Name" : "sj1000-joe-05",
      "SmartAGId" : "sag-d866xl31k8lleb****"
    }, {
      "Name" : "sag1000_box6",
      "SmartAGId" : "sag-dztg1lco3aacpu****"
    }, {
      "Name" : "sag1000-ha-for-case",
      "SmartAGId" : "sag-ewmmi6fcq3gldu****"
    }, {
      "Name" : "ccn-bvt-china-0-0613-003734",
      "SmartAGId" : "sag-fckt58zc4j4b8o****"
    }, {
      "Name" : "sag-sec-2",
      "SmartAGId" : "sag-h4j0klyvprxta5****"
    }, {
      "Name" : "sn-sag1000-2018-11-08-17-27-11",
      "SmartAGId" : "sag-h79g3zs0q7nk9f****"
    }, {
      "Name" : "sag1000_sh_upgrade",
      "SmartAGId" : "sag-mrrrlh3xgpyipu****"
    }, {
      "Name" : "ccn-bvt-china-0-0625-021924",
      "SmartAGId" : "sag-ruia2xefxbdm5e****"
    }, {
      "Name" : "chengxi_bigbox_cn",
      "SmartAGId" : "sag-sb7t1efidyc5d5****"
    }, {
      "Name" : "sj1000-joe_03",
      "SmartAGId" : "sag-srgxemiqbyzdxf****"
    }, {
      "Name" : "sj1000-yf-01",
      "SmartAGId" : "sag-tzirqx07bvcngm****"
    }, {
      "Name" : "ccn-bvt-china-0-0426-005001",
      "SmartAGId" : "sag-xboakpuqext95x****"
    } ]
  },
  "Count" : 20,
  "RequestId" : "C850C10E-9856-45FF-8640-80288BA467DF"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|DependencyViolation.FlowLog|This FlowLog instance is bound to an SAG instance.|FlowLog存在资源依赖。|
|400|IncorrectStatus.FlowLog|The current FlowLog instance status does not support this operation.|FlowLog状态非法。|
|400|InvalidFlowLogId.NotFound|The specified FlowLogId does not exist.|根据FlowLogId未找到对应实例。|
|400|MissingParam.FlowLogId|Specify the FlowLogId parameter.|缺少参数FlowLogId。|
|400|OperationFailed.AssociateFlowLog|The operation failed. The specified SAG instance has already been associated with another FlowLog instance.|由于智能接入网关实例已经关联其他FlowLog实例，操作失败。|
|400|OperationUnsupported.AssociateFlowLog|You cannot bind the SAG device of the current version or model to a FlowLog instance.|设备版本或者款型不支持关联FlowLog操作。|
|400|QuotaExceeded.Flowlog|The maximum number of FlowLog instances is exceeded.|flowlog数量超过配额。|
|400|IllegalParam.ActiveAging|The specified ActiveAging is invalid.|参数ActiveAging不合法。|
|400|IllegalParam.InactiveAging|The specified InactiveAging is invalid.|参数InactiveAging不合法。|
|400|IllegalParam.NetflowServerIp|The specified NetflowServerIp is invalid.|参数NetflowServerIp不合法。|
|400|IllegalParam.NetflowServerPort|The specified NetflowServerPort is invalid.|参数NetflowServerPort不合法。|
|400|IllegalParam.NetflowVersion|The specified NetflowVersion is invalid.|参数NetflowVersion不合法。|
|400|IllegalParam.OutputType|The specified OutputType is invalid.|参数OutputType不合法。|
|400|IllegalParam.RegionId|The specified RegionId is invalid.|参数RegionId不合法。|
|400|IllegalParam.SlsRegionId|The specified SlsRegionId is invalid.|参数SlsRegionId不合法。|
|400|IllegalParam.Status|The specified Status parameter is invalid.|参数Status不合法。|
|403|Forbidden|User not authorized to operate on the specified resource.|用户没有操作此资源的权限。|
|403|MissingParameter|The input parameter is missing, please check your input.|输入参数缺失，请检查您的输入。|
|403|InvalidParameter|The specified parameter is invalid.|非法参数。|
|403|InternalError|An internal server error occurred.|内部服务错误。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

