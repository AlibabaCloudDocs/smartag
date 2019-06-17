# CreateACL {#doc_api_1139446 .reference}

Creates an Access Control List \(ACL\).

## Debug {#apiExplorer .section}

By using [OpenAPI Explorer](https://api.aliyun.com/#product=Smartag&api=CreateACL), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Name|String|Yes|test| The name of the ACL instance.

 The instance name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter. It cannot start with `http://` or `https://`.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the ACL belongs.|

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|AclId|String|acl-xhwhyuo43l\*\*\*\*\*\*\*\*|The ID of the ACL.|
|RequestId|String|EE837E9F-BD50-4C2B-9E47-260F9D848480|The ID of the request.|

## Examples {#demo .section}

**Request example**

```
http(s)://[Endpoint]/?Name=test 
&RegionId=cn-hangzhou
 &<CommonParameters>
```

**Response example**

-   XML format

    ```
    <CreateACL> <AclId>acl-ohlexqptfhygf4xebg</AclId> 
    <RequestId>EE837E9F-BD50-4C2B-9E47-260F9D848480</RequestId> 
    </CreateACL>
    ```

-   JSON format

    ```
    { 
    "AclId":"acl-ohlexqptfhyg******", 
    "RequestId":"EE837E9F-BD50-4C2B-9E47-260F9D848480" }
    ```


## Error codes { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|403|MissingParameter|The input parameter is missing, please check your input.|The input parameter is missing. Please check your input.|
|403|InvalidName|Name not valid.|The name of the ACL is invalid.|
|403|AclAmountLimit|No more ACL can be created. You can open a ticket to increase the quota of ACLs.|The quota for ACLs has been reached. To increase the quota, open a ticket.|
|403|InternalError|An internal server error occurred.|An internal server error has occurred.|

[See common error codes](https://error-center.aliyun.com/status/product/Smartag)

