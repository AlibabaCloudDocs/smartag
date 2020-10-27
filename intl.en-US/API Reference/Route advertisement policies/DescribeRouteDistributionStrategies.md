# DescribeRouteDistributionStrategies

Queries route advertisement policies.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeRouteDistributionStrategies&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeRouteDistributionStrategies|The operation that you want to perform.

 Set the value to **DescribeRouteDistributionStrategies**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the Smart Access Gateway \(SAG\) instance is deployed. |
|SmartAGId|String|Yes|sag-erx3qta5xg5zyq\*\*\*\*|The ID of the SAG instance. |
|SourceType|String|Yes|cloud|The type of route. Valid values:

 -   **cloud**: Alibaba Cloud-facing routes. These routes allow SAG instance to access resources deployed on Alibaba Cloud.
-   **local**: private network-facing routes. These routes allow SAG instances to communicate with on-premises terminals. |
|PageNumber|Integer|No|1|The number of the page to return . Pages start from page 1. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Default value: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|10|The number of entries to return on each page. |
|RequestId|String|944C2533-1BB7-4578-B6EB-DA05BB61C02A|The ID of the request. |
|Strategies|Array| |The list of route advertisement policies. |
|Strategy| | | |
|ConflictInfo|String|"10.90.6.0/24":"vbr-wz900pom71qyr6x67qz65,vbr-wz9f8icxnlcom7riz0gfx"|The information about overlapped routes. |
|CreateTime|Long|1144445|The timestamp that indicates when the health check instance was created. Unit: millisecond. |
|DestCidrBlock|String|192.168.3.0/24|The destination CIDR block. |
|HcInstanceId|String|hc-sztovuprqzgm50\*\*\*\*|The ID of the health check instance. |
|IsConflict|Boolean|false|Indicates whether routes are overlapped. Valid values:

 -   **true**: overlapped.
-   **false**: no |
|RouteDistribution|String|publish|The route advertisement policy. Valid values:

 -   **published**: advertises routes.
-   **no\_publish**: does not advertise routes.
-   **no\_publish\_and\_publish\_on\_health\_success**: routes are only advertised when they pass health check.
-   **no\_publish\_and\_publish\_on\_health\_fail**: routes are advertised only when they fail health check.
-   **publish\_and\_revoke\_on\_health\_success**: advertised routes are only withdrawn when they pass health check.
-   **publish\_and\_revoke\_on\_health\_fail**: advertised routes are withdrawn only when they fail health check.

 For more information, see [Configure health check](~~163971~~) and [Advertise routes](~~163973~~). |
|RouteSource|String|STATIC|The source of routes. Valid values:

 -   **Alibaba Cloud-facing routes**
    -   **The ID of the Virtual Private Cloud \(VPC\)**: learns routes from the VPC network.
    -   **The ID of the virtual border router \(VBR\)**: learns routes from the VBR.
    -   **The ID of the SAG instance**: learns routes from the SAG instance.
-   **Private network-facing routes**
    -   **STATIC**: static routes specified in the SAG console.
    -   **OSPF**: learns routes through the Open Shortest Path First \(OSPF\) protocol.
    -   **BGP**: learns routes through Border Gateway Protocol \(BGP\). |
|SmartAGId|String|sag-erx3qta5xg5zyq\*\*\*\*|The ID of the SAG instance. |
|SourceType|String|cloud|The type of route. Valid values:

 -   **cloud**: Alibaba Cloud-facing routes.
-   **local**: private network-facing routes. |
|Status|String|normal|The route status. Valid values:

 -   **normal**: The route works as expected.
-   **revoked**: The route has been withdrawn. |
|StrategyPublishStatus|String|publish|The route advertisement status. Valid values:

 -   **published**: The route has been advertised.
-   **not\_publish**: The route has not been advertised. |
|TotalCount|Integer|5|The total number of routes. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeRouteDistributionStrategies
&RegionId=cn-shanghai
&SmartAGId=sag-erx3qta5xg5zyq****
&SourceType=cloud
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeRouteDistributionStrategiesResponse>
  <PageNumber>1</PageNumber>
  <TotalCount>2</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>944C2533-1BB7-4578-B6EB-DA05BB61C02A</RequestId>
  <Strategies>
        <Strategy>
              <SmartAGId>sag-erx3qta5xg5zyq****</SmartAGId>
              <Status>normal</Status>
              <RouteSource>STATIC</RouteSource>
              <SourceType>local</SourceType>
              <IsConflict>false</IsConflict>
              <DestCidrBlock>192.168.10.0/24</DestCidrBlock>
        </Strategy>
        <Strategy>
              <SmartAGId>sag-erx3qta5xg5zyq****</SmartAGId>
              <Status>normal</Status>
              <RouteSource>STATIC</RouteSource>
              <SourceType>local</SourceType>
              <IsConflict>false</IsConflict>
              <DestCidrBlock>192.168.11.0/24</DestCidrBlock>
        </Strategy>
  </Strategies>
</DescribeRouteDistributionStrategiesResponse>
```

`JSON` format

```
{
	"PageNumber": 1,
	"TotalCount": 2,
	"PageSize": 10,
	"RequestId": "944C2533-1BB7-4578-B6EB-DA05BB61C02A",
	"Strategies": {
		"Strategy": [
			{
				"SmartAGId": "sag-erx3qta5xg5zyq****",
				"Status": "normal",
				"RouteSource": "STATIC",
				"SourceType": "local",
				"IsConflict": false,
				"DestCidrBlock": "192.168.10.0/24"
			},
			{
				"SmartAGId": "sag-erx3qta5xg5zyq****",
				"Status": "normal",
				"RouteSource": "STATIC",
				"SourceType": "local",
				"IsConflict": false,
				"DestCidrBlock": "192.168.11.0/24"
			}
		]
	}
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|SAG.InstanceIdEmpty|You must specify the SAG instance ID.|The error message returned because the SAG instance ID is not specified.|
|400|SAG.InstanceNoFound|The specified SAG instance does not exist.|The error message returned because the specified SAG instance does not exist.|
|400|RD.InvalidSourceType|The specified route source type is invalid.|The error message returned because the type of the specified route source is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

