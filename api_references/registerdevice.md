# registerDevice

## Description

Use **HTTPs POST** to register devices with or without serial keys

## Request URL

```
https://api.mediatek.com/mcs/v2/devices

```

## Action
HTTPs POST

## Parameters

### Header

Authorization: Bearer '{token}'

### Body
The request body should be constructed in JSON format with the following fields:

| Field Name | Type | Required |Description|
| --- | --- | --- | --- |
| prodId | String | Yes | Product ID |
| name | String | Yes | Device Name |
| isTest | Bool | Yes | Is the device a test device |
| description | String | No | Device Description |
| serial | String | No | Denpends on the product registration criteria defined by developers. Not needed if isTest is true |
| deviceImageURL | String | No | URL of the device image |




## Response

### Response Code
200

### Response Header

Content-Type:`application/json`
### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| deviceId | String | Device ID |
| deviceKey | String | Device Key |
| chipName | String | Chip Name |

**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/devices
```

Request Body

```
{

         "prodId":"b1234567890",
         "name":"My 2nd device",
         "isTest":false,
         "serial":"mtk-01234",
         "deviceImageURL":"/device/mydevice.jpg"

}
```

Response Body

```
{

         "deviceId":"d1234567890",
         "deviceKey":"0987654321d",
         "chipName":"MT7681"

}
```

## Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | Integer | Error Code |
| url | String | url to API Error detail page |
| description | String | Error Description |

**Example:**

```
{
  "results": {
    "code": 1002,
    "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```
