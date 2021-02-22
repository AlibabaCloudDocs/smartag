# DescribeGrantSagVbrRules

Queries authorization information about Smart Access Gateway \(SAG\) instances and cross-account virtual border routers \(VBRs\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Smartag&api=DescribeGrantSagVbrRules&type=RPC&version=2018-03-13)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|DescribeGrantSagVbrRules|The operation that you want to perform.

Set the value to**DescribeGrantSagVbrRules**. |
|RegionId|String|Yes|cn-shanghai|The ID of the region where the SAG instance is deployed. |
|SmartAGId|String|Yes|sag-0nnteglltw6z4b\*\*\*\*|The ID of the SAG instance. |
|VbrInstanceId|String|Yes|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|The ID of the VBR. |
|PageNumber|Integer|No|1|The number of the page to return. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Default value:**10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GrantRules|Array of GrantRule| |The information about the authorization rule. |
|GrantRule| | | |
|Bound|Boolean|false|Indicates whether the SAG instance is associated with the VBR. Valid values:

-   **false**: not associated.
-   **true**: associated. |
|CreateTime|Long|1600743723000|The time when the rule was created. |
|InstanceId|String|sgv-3x8djyem7vqh70\*\*\*\*|The ID of the authorization rule. |
|SmartAGId|String|sag-0nnteglltw6z4b\*\*\*\*|The ID of the SAG instance. |
|SmartAGUid|Long|1231571212121212|The user ID \(UID\) of the account to which the SAG instance belongs. |
|VbrInstanceId|String|vbr-bp13gtbhdp0pfqg6s\*\*\*\*|The ID of the VBR. |
|VbrRegionId|String|cn-hangzhou|The ID of the region where the VBR is deployed. |
|VbrUid|Long|1231571212121212|The user ID \(UID\) of the VBR. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|46E98E69-FBA2-423E-9E5A-A3C6D843FED1|The ID of the request. |
|TotalCount|Integer|1|The total number of authorization rules. |

## Examples

Sample request

```
http(s)://[Endpoint]/? Action=DescribeGrantSagVbrRules
&RegionId=cn-shanghai
&SmartAGId=sag-0nnteglltw6z4b****
&VbrInstanceId=vbr-bp13gtbhdp0pfqg6s****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeGrantSagVbrRulesResponse>
  <TotalCount>1</TotalCount>
  <RequestId>46E98E69-FBA2-423E-9E5A-A3C6D843FED1</RequestId>
  <PageSize>10</PageSize>
  <PageNumber>1</PageNumber>
  <GrantRules>
        <GrantRule>
              <VbrUid>123157908552****</VbrUid>
              <SmartAGUid>168840159596****</SmartAGUid>
              <VbrInstanceId>vbr-bp13gtbhdp0pfqg6s****</VbrInstanceId>
              <InstanceId>sgv-3x8djyem7vqh70****</InstanceId>
              <CreateTime>1600743723000</CreateTime>
              <Bound>false</Bound>
              <VbrRegionId>cn-hangzhou</VbrRegionId>
              <SmartAGId>sag-0nnteglltw6z4b****</SmartAGId>
        </GrantRule>
  </GrantRules>
</DescribeGrantSagVbrRulesResponse>
```

`JSON` format

```
{
    "TotalCount": 1,
    "RequestId": "46E98E69-FBA2-423E-9E5A-A3C6D843FED1",
    "PageSize": 10,
    "PageNumber": 1,
    "GrantRules": {
        "GrantRule": [
            {
                "VbrUid": "123157908552****",
                "SmartAGUid": "168840159596****",
                "VbrInstanceId": "vbr-bp13gtbhdp0pfqg6s****",
                "InstanceId": "sgv-3x8djyem7vqh70****",
                "CreateTime": 1600743723000,
                "Bound": false,
                "VbrRegionId": "cn-hangzhou",
                "SmartAGId": "sag-0nnteglltw6z4b****"
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

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Smartag).

