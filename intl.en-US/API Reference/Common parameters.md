# Common parameters {#reference_xry_cjk_qdb .reference}

## Common request parameters {#section_zm5_rgf_cz .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Format|String|No|The format of the response. Valid values:JSON \(default\) | XML 

|
|Version|String|Yes|The API version in the format of `YYYY-MM-DD`. Valid value:2018-03-13

|
|AccessKeyId|String|Yes|The AccessKey ID of the user who calls the API.|
|Signature|String|Yes|The signature result string.|
|SignatureMethod|String|Yes|The algorithm used to create the request signature. Valid value:HMAC-SHA1

|
|Timestamp|String|Yes|The time at which the request is signed in the `YYYY-MM-DDThh:mm:ssZ` format.Example: 2014-05-26T12:00:00Z.

|
|SignatureVersion|String|Yes|The signature algorithm version to use. Valid value:1.0

|
|SignatureNonce|String|Yes|A unique random number used to prevent network replay attacks.Each request must use a unique random number.

|
|ResourceOwnerAccount|String|No|The account of the owner of the requested resource. Use the logon account name.|

Examples

```

https://smartag.aliyuncs.com/?Action=DescribeSmartAccessGateways
&Format=xml
&Version=2018-03-13
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2018-04-01T12:00:00Z
```

## Common response parameters {#section_rjn_1hf_cz .section}

A `RequestId` is always returned, even if the request is unsuccessful.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!—The root node of the result-->
        <Action+Response>
            <!—The returned result-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!—The returned result-->
        </Action+Response>
    
    ```

-   JSON format:

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*The returned result*/
        }
    ```


