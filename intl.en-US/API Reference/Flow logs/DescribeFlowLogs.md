# DescribeFlowLogs

You can call this operation to query a flow log.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeFlowLogs&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeFlowLogs|The operation that you want to perform.

 Set the value to **DescribeFlowLogs**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the flow log is deployed. |
|FlowLogId|String|No|fl-7a56mar1kfw9vj\*\*\*\*|The ID of the flow log. |
|FlowLogName|String|No|DDE|The name of the flow log. |
|Description|String|No|desc|The description of the flow log. |
|Status|String|No|Active|The status of the flow log. Valid values:

 -   **Active**: The flow log is enabled.
-   **Inactive**: The flow log is disabled. |
|OutputType|String|No|sls|The location where the flow log is stored. Valid values:

 -   **sls**: The flow log is stored in Log Service.
-   **netflow**: The flow log is stored on a NetFlow collector.
-   **all**: The flow log is stored both in Log Service and on a NetFlow collector. |
|PageSize|Integer|No|10|The number of entries to return on each page. Maximum value: **50**. Default value: **10**. |
|PageNumber|Integer|No|1|The number of the page to return. Default value: **1**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|FlowLogs|Array| |Flow log |
|FlowLogSetType| | | |
|ActiveAging|Integer|300|The time interval at which log data of active connections is collected. Valid values: **60 to 6000**. Default value: **300**. Unit: second. |
|Description|String|aaa|The description of the flow log. |
|FlowLogId|String|fl-7a56mar1kfw9vj\*\*\*\*|The ID of the flow log. |
|InactiveAging|Integer|15|The time interval at which log data of inactive connections is connected. Valid values: **10 to 600**. Default value: **15**. Unit: second. |
|LogstoreName|String|config-operation-log|The name of the Log Service Logstore. |
|Name|String|DDE|The name of the flow log. |
|NetflowServerIp|String|192.168.0.xxxx|The IP address of the NetFlow collector where the flow log is stored. |
|NetflowServerPort|String|9995|The port of the NetFlow collector. Default value: **9995**. |
|NetflowVersion|String|V9|The NetFlow version. Default value: **V9**. |
|OutputType|String|sls|The location where the flow log is stored. Valid values:

 -   **sls**: The flow log is stored in Log Service.
-   **netflow**: The flow log is stored on a NetFlow collector.
-   **all**: The flow log is stored both in Log Service and on a NetFlow collector. |
|ProjectName|String|sag-flowlog-shanghai|The name of the Log Service project. |
|SlsRegionId|String|cn-shanghai|The ID of the region where Log Service is deployed. |
|Status|String|Active|The status of the flow log. Valid values:

 -   **Active**: The flow log is enabled.
-   **Inactive**: The flow log is disabled. |
|TotalSagNum|Integer|2|The number of Smart Access gateway \(SAG\) instances with which the flow log is associated. |
|PageNumber|Integer|1|The page number of the returned page. Default value: **1**. |
|PageSize|Integer|10|The number of entries returned per page. Maximum value: **50**. Default value: **10**. |
|RequestId|String|44F4E2D0-77F7-4DEC-969B-061688946143|The ID of the request. |
|TotalCount|Integer|5|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeFlowLogs
&RegionId=cn-hangzhou
&<Common request parameter>
```

Sample success responses

`XML` format

```
<DescribeFlowLogsResponse>
  <TotalCount>1</TotalCount>
  <FlowLogs>
        <FlowLogSetType>
              <NetflowServerPort>9995</NetflowServerPort>
              <Status>Active</Status>
              <LogstoreName>config-operation-log</LogstoreName>
              <Description>aaa</Description>
              <ActiveAging>300</ActiveAging>
              <ProjectName>sag-flowlog-shanghai</ProjectName>
              <NetflowVersion>V9</NetflowVersion>
              <InactiveAging>15</InactiveAging>
              <FlowLogId>fl-0vv40lyu2un5qh****</FlowLogId>
              <Name>test</Name>
              <TotalSagNum>0</TotalSagNum>
              <SlsRegionId>cn-shanghai</SlsRegionId>
              <OutputType>sls</OutputType>
        </FlowLogSetType>
  </FlowLogs>
  <RequestId>6F959528-F177-488C-93DA-6A791BBC718B</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>1</PageNumber>
</DescribeFlowLogsResponse>
```

`JSON` format

```
{
	"TotalCount": 1,
	"FlowLogs": {
		"FlowLogSetType": [
			{
				"NetflowServerPort": 9995,
				"Status": "Active",
				"LogstoreName": "config-operation-log",
				"Description": "aaa",
				"ActiveAging": 300,
				"ProjectName": "sag-flowlog-shanghai",
				"NetflowVersion": "V9",
				"InactiveAging": 15,
				"FlowLogId": "fl-0vv40lyu2un5qh****",
				"Name": "test",
				"TotalSagNum": 0,
				"SlsRegionId": "cn-shanghai",
				"OutputType": "sls"
			}
		]
	},
	"RequestId": "6F959528-F177-488C-93DA-6A791BBC718B",
	"PageSize": 10,
	"PageNumber": 1
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

