# deregisterDevice

### Description

Use **HTTPs DELETE** to deregister an registered device

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:deviceId?removeData=:removeDataStatus

```

### Action
HTTPs POST

### Parameters

#### Header

Authorization: Bearer '{token}'

#### Query String
Following fields should be constructed and appended to the end of the URL:

| Field Name | Type | Required |Description|
| --- | --- | --- | --- |
| removeDataStatus | Bool | No | Sepcify 'true' if aslo removing data on the cloud |




### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| deviceId | String | Device ID |
| deregisteredAt | Number | Timestamp of deregistration |


**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/devices/:device_id?remove_data=true
```

Response Body

```
{
   "deviceId":"c1234567890",
   "deregisteredAt":946684800
}
```

### Error Response

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
