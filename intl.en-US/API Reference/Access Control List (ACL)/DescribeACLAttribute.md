# DescribeACLAttribute {#doc_api_1162752 .reference}

Queries the configurations of an Access Control List \(ACL\).

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DescribeACLAttribute), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DescribeACLAttribute|The name of this action. Value: **DescribeACLAttribute**|
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*|The ID of the ACL.|
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs.|
|Direction|String|No|test|The direction of the ACL.|
|Order|String|No|1255444444|The order number of the ACL.|
|PageNumber|Integer|No|2|The number of pages to return. Default value: 1.|
|PageSize|Integer|No|10|The number of entries per page. Maximum value: 50. Default value: 10.|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Acrs|N/A|N/A|A list of ACL rules.|
|└AclId|String|acl-xhwhyuo43l\*\*\*\*\*\*\*|The ID of the ACL.|
|└AcrId|String|acr-oicr94jwtpij\*\*\*\*\*\*\*|The ID of the ACL rule.|
|└Description|String|Access rule|The description of the ACL rule. It must be 1 to 512 characters in length.|
|└DestCidr|String|0.0.0.0/0|The destination address. It is an IPv4 address range in the CIDR format. Default value: 0.0.0.0/0 |
|└DestPortRange|String|12|The range of the destination port. Valid value: 80/80.|
|└Direction|String|in|The direction of the ACL rule. Valid values: in|out|
|└GmtCreate|Long|1553077933000|The time at which the ACL rule was created.|
|└IpProtocol|String|TCP|The protocol used by the ACL rule. The value is not case sensitive.|
|└Policy|String|drop|The policy used by the ACL rule. Default value: drop|accept.|
|└Priority|Integer|2|The priority of the ACL rule. Value range: 1 to 100. Default value: 1.|
|└SourceCidr|String|0.0.0.0/0|The source address. It is an IPv4 address range in the CIDR format. Default value: 0.0.0.0/0 |
|└SourcePortRange|String|30|The range of the source port. Valid value: 80/80|
|PageNumber|Integer|12|The number of pages to return.|
|PageSize|Integer|5|The number of entries per page.|
|RequestId|String|5DC67C13-B0E4-45E0-A60C-D32D3B74AB19|The ID of the request.|
|TotalCount|Integer|12|The number of queried entries.|

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-ohlexqptfhy******
&RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

-   XML format

    ``` {#xml_return_success_demo}
    <DescribeACLAttribute>
      <PageNumber>1</PageNumber>
      <Acrs>
        <Acr>
          <IpProtocol>TCP</IpProtocol>
          <SourceCidr>192.168.3.0/24</SourceCidr>
          <SourcePortRange>1/65535</SourcePortRange>
          <AclId>acl-xhwhyuo43l0******</AclId>
          <AcrId>acr-oicr94jwtpi*******</AcrId>
          <Policy>accept</Policy>
          <DestPortRange>1/65535</DestPortRange>
          <DestCidr>10.0.0.1/32</DestCidr>
          <GmtCreate>1553077933000</GmtCreate>
          <Direction>out</Direction>
          <Priority>1</Priority>
        </Acr>
      </Acrs>
      <TotalCount>1</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>5DC67C13-B0E4-45E0-A60C-D32D3B74AB19</RequestId>
    </DescribeACLAttribute>
    
    ```

-   JSON format

    ``` {#json_return_success_demo}
    {
    	"PageNumber":1,
    	"Acrs":{
    		"Acr":[
    			{
    				"IpProtocol":"TCP",
    				"SourceCidr":"192.168.3.0/24",
    				"SourcePortRange":"1/65535",
    				"AcrId":"acr-oicr94jwtpi******",
    				"AclId":"acl-xhwhyuo43l0n******",
    				"Policy":"accept",
    				"DestPortRange":"1/65535",
    				"DestCidr":"10.0.0.1/32",
    				"GmtCreate":1553077933000,
    				"Direction":"out",
    				"Priority":1
    			}
    		]
    	},
    	"TotalCount":1,
    	"PageSize":10,
    	"RequestId":"5DC67C13-B0E4-45E0-A60C-D32D3B74AB19"
    }
    ```


## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidParameter|The specified parameter is invalid.|The input parameter is invalid.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The ID of the ACL group is invalid.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

