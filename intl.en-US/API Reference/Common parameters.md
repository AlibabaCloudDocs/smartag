# Common parameters

## Common request parameters

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Format|String|No|The format in which the response is returned. Valid values: JSON and XML. Default value: JSON. |
|Version|String|Yes|The version number of the API. Format: `YYYY-MM-DD`. Valid values: 2018-03-13 |
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption method of the signature string. Valid values: HMAC-SHA1 |
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the `YYYY-MM-DDThh:mm:ssZ` format. The time must be in UTC. Example: 2013-01-10T12:00:00Z, which indicates 20:00:00 on January 10, 2013 \(UTC+8\). |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to: 1.0 |
|SignatureNonce|String|Yes|A unique, random number used to prevent replay attacks. You must use different numbers for multiple requests. |
|ResourceOwnerAccount|String|No|The username of the account that owns the resource that you want to access through this API request.|

Sample requests

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

## Common response parameters

Every response returns a unique RequestID \(`RequestId`\) regardless of whether the call is successful.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!--Result root node-->
        <Operation name+Response>
            <!--Returned request tag-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!--Response parameters-->
        </Operation name+Response>
                        
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Response parameters*/
        }
    ```


