# RevokeInstanceFromCbn {#doc_api_Smartag_RevokeInstanceFromCbn .reference}

Revokes CEN authorization from a CCN.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Smartag&api=RevokeInstanceFromCbn&type=RPC&version=2018-03-13)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CcnInstanceId|String|Yes|ccn-n2935s1mnwv8i\*\*\*\*\*|The ID of the CCN instance.

 |
|CenInstanceId|String|Yes|cen-7qthudw0ll6jm\*\*\*\*\*|The ID of the CEN instance.

 |
|RegionId|String|Yes|cn-shanghai|The ID of the region.

 |
|Action|String|No|RevokeInstanceFromCbn|The name of this action. Value: **RevokeInstanceFromCbn**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|07D73949-2508-4169-8C64-7CCDB33871C4|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=RevokeInstanceFromCbn
&CcnInstanceId=ccn-n2935s1mnwv8i*****
&CenInstanceId=cen-7qthudw0ll6jm*****
&RegionId=cn-shanghai
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<RevokeInstanceFromCbnResponse>
	  <RequestId>07D73949-2508-4169-8C64-7CCDB33871C4</RequestId>
</RevokeInstanceFromCbnResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"07D73949-2508-4169-8C64-7CCDB33871C4"
}
```

## Errors { .section}

