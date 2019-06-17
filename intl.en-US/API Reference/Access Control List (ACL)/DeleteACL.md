# DeleteACL {#doc_api_1162882 .reference}

Deletes an Access Control List \(ACL\).

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=DeleteACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example|Description|
|---------|----|---------|-------|-----------|
|AclId|String|Yes|acl-ohlexqptfhy\*\*\*\*\*\*\*|The ID of the ACL.|
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs.|
|Action|String|No|DeleteACL|The name of this action. Value:DeleteACL|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|00546174-2CE6-4587-9550-04B6A3313938|The ID of the request.|

## Examples {#demo .section}

**Request example**

``` {#request_demo}

http(s)://[Endpoint]/?AclId=acl-ohlexqptfhy*******
&RegionId=cn-hangzhou
&<CommonParameters>

```

**Response example**

-   XML format

    ``` {#xml_return_success_demo}
    <DeleteACL>
      <RequestId>00546174-2CE6-4587-9550-04B6A3313938</RequestId>
    </DeleteACL>
    
    ```

-   JSON format

    ``` {#json_return_success_demo}
    {
    	"RequestId":"00546174-2CE6-4587-9550-04B6A3313938"
    }
    ```


## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidId.ACL|The specified ACL ID is invalid.|The ID of the ACL is invalid.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|The current version of the Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|The current version of the active Smart Access Gateway device does not support this feature.|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|The current version of the standby Smart Access Gateway device does not support this feature.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

