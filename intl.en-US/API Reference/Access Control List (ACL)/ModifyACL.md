# ModifyACL {#doc_api_1162786 .reference}

Modifies an Access Control List \(ACL\).

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=ModifyACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|AclId|String|Yes|acl-e30a66to95cs\*\*\*\*\*\*|The ID of the ACL.|
|Name|String|Yes|test|The name of the ACL.|
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs.|
|Action|String|No|ModifyACL|The name of this action. Value: ModifyACL|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|076FD0BE-67D5-4338-A2A1-C54DE7D78B16|The ID of the request.|

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-e30a66to95cs******
&Name=test
&RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

-   XML format

    ``` {#xml_return_success_demo}
    <ModifyACL>
      <RequestId>076FD0BE-67D5-4338-A2A1-C54DE7D78B16</RequestId>
    </ModifyACL>
    
    ```

-   JSON format

    ``` {#json_return_success_demo}
    {
    	"RequestId":"076FD0BE-67D5-4338-A2A1-C54DE7D78B16"
    }
    ```


## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidName|Name not valid.|The name of the ACL is invalid.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The ID of the ACL is invalid.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

