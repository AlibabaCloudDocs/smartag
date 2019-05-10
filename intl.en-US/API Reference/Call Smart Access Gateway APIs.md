# Call Smart Access Gateway APIs {#concept_pq3_xjs_j2b .concept}

To call a Smart Access Gateway API, you can send an HTTP GET request to the address of the Smart Access Gateway API server, and add request parameters in the request according to the API description. The system then returns the result. The request and the response are encoded using the UTF-8 character set.

## Request structure {#section_wqz_yyt_j2b .section}

Smart Access Gateway APIs are of the RPC type. You can call Smart Access Gateway APIs by sending HTTP GET requests.

The request structure is as follows:

```
http://endpoint/?Action=xx&parameters
```

where:

-   Endpoint: The entry of the Alibaba Cloud service to call. The end point of Smart Access Gateway is smartag.cn-shanghai.aliyuncs.com.
-   Action: The action to perform. For example, use the DescribeSmartAccessGateways API to query created Smart Access Gateway instances.
-   Version: The version of the VPI to use. The version of the Smart Access Gateway APIs is 2018-03-13.
-   Parameters: Request parameters separated by ampersands \(&\).

    Request parameters consist of common parameters and API specific parameters. Common parameters include API version, credentials and more.


The following example uses the DescribeSmartAccessGateways API to query the created Smart Access Gateway instances:

For easy reading, the API request is displayed in the following format in the document:

```

https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGateways
&Format=xml
&Version=2018-03-13
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2018-04-01T12:00:00Z
```

## API authorization {#section_thk_g15_j2b .section}

For security purposes, we recommend that you grant a RAM account the permission to call APIs. Before a RAM user can start to call APIs, you must grant the RAM user permission by creating an authorization policy and attaching the policy to the RAM user. For more information, see [RAM authentication](intl.en-US/API Reference/RAM authentication.md#).

## API signature {#section_kld_s15_j2b .section}

To ensure the security of your API, you must sign the API request. Alibaba Cloud then uses the signature in the request to verify the identity of the user who calls the API.

Smart Access Gateway uses AccessKeyId and AccessKeySecret for symmetric encryption to verify the identity of the caller. AccessKey is a type of credential \(similar to password\) for Alibaba Cloud accounts and RAM users, where the AccessKeyId identifies the callers and the AccessKeySecret is a secret key for encrypting and verifying the signature string. The AccessKeySecret must be kept confidential.

For more information, see [RPC API signature](https://www.alibabacloud.com/help/doc-detail/66384.htm).

For an RPC API, you must add the signature to the API request in the following format:

```
https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
```

Take DescribeSmartAccessGateways as an example. If the AccessKey ID is testid, the AccessKey Secret is testsecret, and the original request URL is as follows:

```

https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGateways
&Timestamp=2016-04-23T12:46:24Z
&Format=XML
&AccessKeyId=testid
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&Version=2018-03-13
&SignatureVersion=1.0
```

To calculate the signature, follow these steps:

1.  Use the request parameters to create a canonicalized query string to sign.

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%DescribeSmartAccessGateways&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&Timestamp%3D2018-04-23T12%253A46%253A24Z&Version%3D2018-03-13
    ```

2.  Calculate the HMAC value of the string to sign according to RFC 2104. The key used for calculation is the AccessKey Secret appended with an ampersand \(&\). In this example, the key is `testsecret&amp;`.

    The resulting signature in this example is as follows:

    ```
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    ```

3.  Add the signature to the request URL.

    ```
    
    https://smartag.cn-shanghai.aliyuncs.com/?Action=DescribeSmartAccessGateways
    &Timestamp=2016-04-23T12:46:24Z
    &Format=XML
    &AccessKeyId=testid
    &SignatureMethod=HMAC-SHA1
    &SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
    &Version=2018-03-13
    &SignatureVersion=1.0
    &Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D
    ```


