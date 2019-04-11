# 调用API {#concept_pq3_xjs_j2b .concept}

智能接入网关接口调用是通过向智能接入网关API的服务端地址发送HTTP GET请求，请按照接口说明在请求中加入相应请求参数，调用后系统会返回处理结果。请求及返回结果都使用UTF-8字符集进行编码。

## 请求结构 {#section_wqz_yyt_j2b .section}

智能接入网关的API是RPC风格，您可以通过发送HTTP GET请求调用智能接入网关API。

其请求结构如下：

```
http://endpoint/?Action=xx&parameters
```

其中：

-   Endpoint：智能接入网关API的服务接入地址为 smartag.cn-shanghai.aliyuncs.com。
-   Action：要执行的操作，如使用DescribeSmartAccessGateways查询已创建的智能接入网关实例。
-   Version：要使用的API版本，智能接入网关的API版本是2018-03-13。
-   Parameters：请求参数，每个参数之间用“&”分隔。

    请求参数由公共请求参数和API自定义参数组成。公共参数中包含API版本号、身份验证等信息。


下面是一个调用DescribeSmartAccessGateways接口查询已创建的智能接入网关实例的示例：

为了便于用户查看，本文档中的示例都做了格式化处理。

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

## API授权 {#section_thk_g15_j2b .section}

为了确保您的账号安全，建议您使用子账号的身份凭证调用API。如果您使用RAM账号调用智能接入网关API，您需要为该RAM账号创建、附加相应的授权策略。详情参见[RAM鉴权](intl.zh-CN/API参考/RAM鉴权.md#)。

## API签名 {#section_kld_s15_j2b .section}

智能接入网关服务会对每个API请求进行身份验证，无论使用HTTP还是HTTPS协议提交请求，都需要在请求中包含签名（Signature）信息。

智能接入网关通过使用AccessKey ID和AccessKey Secret进行对称加密的方法来验证请求的发送者身份。AccessKey是为阿里云账号和RAM用户发布的一种身份凭证\(类似于用户的登录密码\)，其中AccessKey ID 用于标识访问者的身份，AccessKey Secret是用于加密签名字符串和服务器端验证签名字符串的密钥，必须严格保密。

关于如何计算签名，参见[RPC API签名](https://www.alibabacloud.com/help/doc-detail/66384.htm)。

RPC API需按如下格式在请求中增加签名（Signature）：

```
https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
```

以DescribeSmartAccessGateways为例，假设AccessKey ID是testid， AccessKey Secret是testsecret，则签名前的请求URL如下：

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

完成以下步骤计算签名：

1.  使用请求参数创建待签名字符串：

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%DescribeSmartAccessGateways&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&Timestamp%3D2018-04-23T12%253A46%253A24Z&Version%3D2018-03-13
    ```

2.  计算待签名的HMAC的值，在AccessKey Secret后添加一个“&”作为计算HMAC值的key。本示例中的key为`testsecret&`。

    计算后得到的签名为：

    ```
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    ```

3.  将签名加到请求参数中：

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


