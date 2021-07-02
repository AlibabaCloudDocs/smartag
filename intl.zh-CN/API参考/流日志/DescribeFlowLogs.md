# DescribeFlowLogs

调用DescribeFlowLogs查询指定地域下流日志实例信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=DescribeFlowLogs&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeFlowLogs|系统规定参数。取值：**DescribeFlowLogs**。 |
|RegionId|String|是|cn-shanghai|流日志实例所属地域ID。 |
|FlowLogId|String|否|fl-7a56mar1kfw9vj\*\*\*\*|流日志实例ID。 |
|FlowLogName|String|否|DDE|流日志实例名称。 |
|Description|String|否|desc|流日志实例描述。 |
|Status|String|否|Active|流日志实例状态，取值：

 -   **Active**：已启动。
-   **Inactive**：未启动。 |
|OutputType|String|否|all|流日志输出类型，取值：

 -   **sls**：流日志存储在阿里云日志服务中。
-   **netflow**：流日志存储在您配置的NetFlow服务器上。
-   **all**：流日志同时存储在阿里云日志服务和您配置的NetFlow服务器上。 |
|PageSize|Integer|否|10|分页查询时每页的条目数，默认值为**10**。 |
|PageNumber|Integer|否|1|查询页码，默认值为**1**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|TotalCount|Integer|5|总条目数。 |
|FlowLogs|Array of FlowLogSetType| |流日志实例信息列表。 |
|FlowLogSetType| | | |
|Status|String|Active|流日志实例的状态：

 -   **Active**：已启动。
-   **Inactive**：未启动。 |
|TotalSagNum|Integer|2|流日志实例关联的智能接入网关实例数目。 |
|NetflowServerIp|String|192.168.0.1|存储流日志的Netflow服务器地址。 |
|ProjectName|String|sag-flowlog-shanghai|日志服务的Project名称。 |
|SlsRegionId|String|cn-shanghai|日志服务的地域ID。 |
|ActiveAging|Integer|300|活跃流输出间隔。单位：秒。 |
|OutputType|String|sls|流日志输出类型。

 -   **sls**：流日志存储在阿里云日志服务中。
-   **netflow**：流日志存储在您配置的Netflow服务器上。
-   **all**：流日志同时存储在阿里云日志服务和您配置的Netflow服务器上。 |
|Description|String|aaa|流日志实例描述。 |
|NetflowVersion|String|V9|存储流日志的Netflow协议版本号，默认值为**V9**。 |
|InactiveAging|Integer|15|非活跃流输出间隔。单位：秒。 |
|NetflowServerPort|String|9995|存储流日志的Netflow服务器端口，默认值为**9995**。 |
|Name|String|DDE|流日志实例名称。 |
|FlowLogId|String|fl-7a56mar1kfw9vj\*\*\*\*|流日志实例ID。 |
|LogstoreName|String|config-operation-log|日志服务的日志库名称。 |
|ResourceGroupId|String|rg-acfm2iu4fnc\*\*\*\*|流日志实例所属的资源组ID。 |
|PageSize|Integer|10|分页查询时每页的条目数。 |
|RequestId|String|44F4E2D0-77F7-4DEC-969B-061688946143|请求ID。 |
|PageNumber|Integer|1|查询页码。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeFlowLogs
&RegionId=cn-shanghai
&FlowLogId=fl-7a56mar1kfw9vj****
&FlowLogName=DDE
&Description=desc
&Status=Active
&OutputType=all
&ResourceGroupId=rg-acfm2iu4fnc****
&PageSize=10
&PageNumber=1
&公共请求参数
```

正常返回示例

`XML`格式

```
HTTP/1.1 200 OK
Content-Type:application/xml

<DescribeFlowLogsResponse>
    <TotalCount>1</TotalCount>
    <FlowLogs>
        <FlowLogSetType>
            <Status>Active</Status>
            <NetflowServerPort>9995</NetflowServerPort>
            <LogstoreName>
sag-shanghai</LogstoreName>
            <ActiveAging>300</ActiveAging>
            <ResourceGroupId>rg-acfm2iu4fnc****</ResourceGroupId>
            <ProjectName>sag-flowlog-shanghai</ProjectName>
            <NetflowVersion>V9</NetflowVersion>
            <InactiveAging>15</InactiveAging>
            <FlowLogId>fl-49u97c08z42n3f****</FlowLogId>
            <Name>zxtest</Name>
            <TotalSagNum>0</TotalSagNum>
            <SlsRegionId>cn-shanghai</SlsRegionId>
            <OutputType>sls</OutputType>
        </FlowLogSetType>
    </FlowLogs>
    <PageSize>10</PageSize>
    <RequestId>67D7003F-9D67-4935-9C47-10C5B3074028</RequestId>
    <PageNumber>1</PageNumber>
</DescribeFlowLogsResponse>
```

`JSON`格式

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "TotalCount" : 1,
  "FlowLogs" : {
    "FlowLogSetType" : [ {
      "Status" : "Active",
      "NetflowServerPort" : 9995,
      "LogstoreName" : "\r\nsag-shanghai",
      "ActiveAging" : 300,
      "ResourceGroupId" : "rg-acfm2iu4fnc****",
      "ProjectName" : "sag-flowlog-shanghai",
      "NetflowVersion" : "V9",
      "InactiveAging" : 15,
      "FlowLogId" : "fl-49u97c08z42n3f****",
      "Name" : "zxtest",
      "TotalSagNum" : 0,
      "SlsRegionId" : "cn-shanghai",
      "OutputType" : "sls"
    } ]
  },
  "PageSize" : 10,
  "RequestId" : "67D7003F-9D67-4935-9C47-10C5B3074028",
  "PageNumber" : 1
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Smartag)查看更多错误码。

