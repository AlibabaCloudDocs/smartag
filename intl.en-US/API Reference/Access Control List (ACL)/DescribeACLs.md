# DescribeACLs {#doc_api_1162779 .reference}

Queries one or more Access Control Lists \(ACLs\) in a region.

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeACLs), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACLs belongs.|
|AclIds|String|No|acl-xhwhyuo43l\*\*\*\*\*\*\*|A list of ACL IDs. Separate multiple IDs with commas. If this parameter is not specified, all ACL rules in a region are queried.|
|Action|String|No|DescribeACLs|The name of this action. Value: DescribeACLs.|
|Name|String|No|test|The name of the ACL.|
|PageNumber|Integer|No|1|The number of pages to return. Default value: 1.|
|PageSize|Integer|No|1|The number of entries per page. Maximum value: 50. Default value: 10.|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Acls|N/A|N/A|A list of ACLs.|
|└AclId|String|acl-ohlexqptfhy\*\*\*\*\*\*\*|The ID of the ACL.|
|└Name|String|test|The name of the ACL.|
|└SagCount|String|3|The number of attached SAG instances.|
|PageNumber|Integer|1|The number of pages to return.|
|PageSize|Integer|2|The number of entries per page.|
|RequestId|String|3200E8A3-563F-4FFC-8BDB-0F1263FA69E8|The ID of the request.|
|TotalCount|Integer|3|The number of queried entries.|

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

-   XML format

    ``` {#xml_return_success_demo}
    <DescribeACLs>
      <PageNumber>1</PageNumber>
      <TotalCount>3</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>3200E8A3-563F-4FFC-8BDB-0F1263FA69E8</RequestId>
      <Acls>
        <Acl>
          <Name>vmeixme</Name>
          <SagCount>0</SagCount>
          <AclId>acl-e30a66to95csjy75r9</AclId>
        </Acl>
        <Acl>
          <Name>test</Name>
          <SagCount>0</SagCount>
          <AclId>acl-ohlexqptfhygf4xebg</AclId>
        </Acl>
        <Acl>
          <Name>test</Name>
          <SagCount>3</SagCount>
          <AclId>acl-xhwhyuo43l0n2b832u</AclId>
        </Acl>
      </Acls>
    </DescribeACLs>
    
    ```

-   JSON format

    ``` {#json_return_success_demo}
    {
    	"PageNumber":1,
    	"TotalCount":3,
    	"PageSize":10,
    	"RequestId":"3200E8A3-563F-4FFC-8BDB-0F1263FA69E8",
    	"Acls":{
    		"Acl":[
    			{
    				"Name":"vmeixme",
    				"SagCount":0,
    				"AclId":"acl-e30a66to95csjy75r9"
    			},
    			{
    				"Name":"test",
    				"SagCount":0,
    				"AclId":"acl-ohlexqptfhygf4xebg"
    			},
    			{
    				"Name":"test",
    				"SagCount":3,
    				"AclId":"acl-xhwhyuo43l0n2b832u"
    			}
    		]
    	}
    }
    ```


## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidParameter|The specified parameter is invalid.|The specified parameter is invalid.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

